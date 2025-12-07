# 🔵 Paralelo Virtual TomTech
### Sincronize múltiplos switches e lights como se fossem um único ponto de iluminação.

Este blueprint permite criar um **paralelo virtual** no Home Assistant, sincronizando qualquer quantidade de dispositivos (switches ou lights) para funcionarem juntos — como se estivessem ligados fisicamente no mesmo circuito.

Ideal para:
- Unificar automações entre interruptores diferentes  
- Criar paralelos sem obra (sem alterar a fiação)  
- Integrar relés, módulos, luminárias e lâmpadas inteligentes  
- Sincronizar acionamentos físicos, via app ou voz  

Desenvolvido com foco em simplicidade, eficiência e confiabilidade.

---

# 📦 Funcionalidades

- 🔄 Liga/Desliga todos os dispositivos selecionados simultaneamente  
- ⚡ Resposta rápida e consistente  
- 🚫 Evita conflitos entre automações  
- 📘 Compatível com switches, lights, relés Zigbee, Wi-Fi e Z-Wave  
- 🛡️ Blueprint otimizado para evitar loops e delays excessivos  
- 🔌 Perfeito para projetos profissionais de automação residencial  

---

# 📁 Blueprint YAML

```yaml
blueprint:
  name: Paralelo Virtual TomTech
  description: Sincroniza múltiplos switches/luzes para funcionarem como um único ponto de controle virtual.
  domain: automation

  input:
    dispositivos:
      name: Selecionar Dispositivos
      description: Escolha todos os switches e lights que devem atuar em paralelo.
      selector:
        entity:
          domain:
            - switch
            - light
          multiple: true

mode: restart
max_exceeded: silent

trigger:
  - platform: state
    entity_id: !input dispositivos

action:
  - variables:
      estado: "{{ trigger.to_state.state }}"

  - choose:
      - conditions: "{{ estado == 'on' }}"
        sequence:
          - service: homeassistant.turn_on
            target:
              entity_id: !input dispositivos

      - conditions: "{{ estado == 'off' }}"
        sequence:
          - service: homeassistant.turn_off
            target:
              entity_id: !input dispositivos

  # Pequeno delay para evitar congestionamento em dispositivos Zigbee/Wi-Fi
  - delay: "00:00:01"


---

# 📦 Funcionalidades
  🚀 Como instalar
1. Acesse o Home Assistant
Configurações → Automações e Cenas → Blueprints
Clique em Importar Blueprint
2. Cole o link deste repositório
(URL do seu GitHub)

3. Após importar
Clique em Criar automação usando este blueprint
Escolha todos os dispositivos que farão parte do paralelo virtual

4. Salve e teste
Acione qualquer dispositivo
Todos serão atualizados automaticamente

🛠️ Boas práticas TomTech
Utilize nomes claros nos dispositivos (ex.: sala_lustre, sala_abajur)
Evite misturar dispositivos com latência muito diferente
Se usar Zigbee, mantenha um delay curto (1s é ideal)
Teste acionamentos físicos e via assistente de voz
Evite adicionar dispositivos com comportamento especial (ex.: dimmers RF)
