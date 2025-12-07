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

🧪 Exemplo de uso
💡 Cenário:

Você possui:

switch.sala_lustre

light.sala_led

switch.sala_abajur

Com o blueprint configurado, ao ligar qualquer um, os outros dois ligam juntos.
Ao desligar qualquer um, todos desligam.

🛠️ Boas práticas TomTech

Utilize nomes claros nos dispositivos (ex.: sala_lustre, sala_abajur)

Evite misturar dispositivos com latência muito diferente

Se usar Zigbee, mantenha um delay curto (1s é ideal)

Teste acionamentos físicos e via assistente de voz

Evite adicionar dispositivos com comportamento especial (ex.: dimmers RF)

📄 Changelog
v1.0 — Primeira versão pública

Código otimizado

Reescrita completa e organizada

Adicionado modo restart

Lógica com variables e choose

Delay otimizado para estabilidade

👨‍💻 Autor

Tom Tech (Thomaz Melo)
Automação Residencial • Home Assistant • Homelab
Instagram: @tomtechs
YouTube: youtube.com/@TomTechs

⭐ Gostou do blueprint?

Deixe uma estrela ⭐ no repositório para apoiar o projeto!
Siga o Tom Tech para mais conteúdos de automação residencial.
