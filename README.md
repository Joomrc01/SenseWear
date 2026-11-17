SenseWear — Protótipo 1 (MVP) 🦯🔊
Tecnologia que aproxima.

!Status do Projeto !Hardware !Direitos

📋 1. Sobre o Projeto

O SenseWear é um projeto de tecnologia assistiva desenvolvido com o objetivo de auxiliar pessoas com baixa visão na identificação de obstáculos durante a locomoção.

O objetivo do Protótipo 1 é desenvolver um dispositivo vestível capaz de detectar obstáculos à frente do usuário e emitir alertas por meio de vibrações, contribuindo para uma maior percepção do ambiente.

Atualmente, o projeto encontra-se na fase de desenvolvimento do MVP (Produto Mínimo Viável) em bancada. Nessa etapa, são utilizados um sensor ultrassônico HC-SR04, três LEDs indicadores e um buzzer para validar a leitura de distância e a classificação dos níveis de proximidade.

Após a validação do circuito, será realizada a integração do motor vibratório e o desenvolvimento de um suporte vestível, como uma luva ou pulseira.

⚠️ Aviso de segurança: O SenseWear é uma ferramenta complementar de auxílio à mobilidade. Não substitui a bengala, o cão-guia ou o treinamento de orientação e mobilidade, nem garante a identificação de todos os obstáculos.
📸 2. Fotos do Protótipo (MVP em Bancada)

Esta seção será utilizada para documentar visualmente o desenvolvimento do protótipo atual.

As imagens deverão apresentar a montagem na protoboard e os testes de funcionamento dos componentes.

![Montagem do SenseWear](78d0b2eb-7c52-47df-bbc2-efc1d18800e0.jfif)
![Montagem do SenseWear](ae77f9f8-5386-4ea7-80a1-7b3d4c6c4827.jfif)
![Montagem do SenseWear](c18b51a4-7f48-4877-8e64-016e74ee4eba.jfif)
![Montagem do SenseWear](ff24cfa8-eae9-471b-90a1-197bdc222a7f.jfif)

Wokmi: Projeto MVP em produção (https://wokwi.com/projects/480239124798622721)

🎯 3. Fases e Evolução do Projeto

O desenvolvimento do SenseWear está dividido em três etapas principais:

Etapa	Descrição	Situação
MVP de Bancada	Leitura de distância com HC-SR04, sinalização por LEDs e alerta sonoro com buzzer.	Em montagem e testes
Protótipo 1 — SenseWear Vestível	Integração do motor vibratório e desenvolvimento de suporte para utilização na mão ou no pulso.	Próxima etapa
Versão Futura — SenseWear Guardian	Possível implementação de detecção de remoção, identificação de quedas e envio de SOS com localização.	Fora do escopo atual
⚙️ 4. Funcionamento do Sistema

O funcionamento do SenseWear é baseado em um ciclo contínuo de detecção, processamento e sinalização de obstáculos.

4.1. Detecção

O sensor ultrassônico HC-SR04 realiza a medição da distância entre o dispositivo e o obstáculo localizado à sua frente, enviando as informações ao Arduino Uno.

4.2. Processamento

O Arduino Uno recebe os dados do sensor e compara a distância identificada com três faixas de proximidade previamente definidas no código.

Com base nessa comparação, o sistema classifica o obstáculo em três níveis de risco:

4.3. Sinalização dos Alertas
🟢 LED Verde — Zona Segura: indica que o caminho está livre ou que o obstáculo se encontra a uma distância considerada segura.
🟡 LED Amarelo — Zona de Atenção: indica que existe um obstáculo se aproximando, representando uma zona de alerta preventivo.
🔴 LED Vermelho + Buzzer — Zona de Perigo: indica que o obstáculo está muito próximo. Nessa situação, o buzzer emite um alerta sonoro contínuo ou intermitente, conforme a programação.
4.4. Repetição do Ciclo

O processo de medição, processamento e sinalização é repetido continuamente enquanto o sistema estiver alimentado, permitindo o monitoramento constante do ambiente à frente.

4.5. Fluxograma de Funcionamento
mermaid
flowchart TD
    A[HC-SR04 mede a distância] --> B[Arduino Uno processa a leitura]
    B --> C{Qual a faixa de distância?}
    C -->|Distância segura| D[LED Verde aceso]
    C -->|Zona de atenção| E[LED Amarelo aceso]
    C -->|Zona de perigo| F[LED Vermelho aceso + Buzzer acionado]
    D --> A
    E --> A
    F --> A

🛠️ 5. Componentes do Projeto
5.1. Componentes Utilizados no MVP Atual (Bancada)
Componente	Função	Observação
Arduino Uno	Controlar e processar as informações recebidas pelo sensor.	Unidade principal de processamento.
Sensor ultrassônico HC-SR04	Medir a distância até os obstáculos.	Depende da superfície e do alinhamento frontal.
LED Verde	Indicar a zona segura.	Sinalização visual.
LED Amarelo	Indicar a zona de atenção.	Sinalização visual.
LED Vermelho	Indicar a zona de perigo.	Sinalização visual.
Buzzer	Emitir alertas sonoros.	Acionado quando o obstáculo está muito próximo.
Protoboard	Permitir a montagem temporária do circuito.	Utilizada durante os testes.
Resistores e jumpers	Realizar as conexões elétricas e limitar a corrente dos LEDs.	Componentes auxiliares.
Cabo USB	Permitir a programação e alimentação do Arduino.	Conectado ao computador durante os testes.
5.2. Componentes Previstos para a Versão Vestível
Componente	Função planejada
Motor vibratório 5 V	Produzir alertas táteis por meio de vibrações.
Transistor ou driver	Realizar o acionamento adequado do motor vibratório, sem conectá-lo diretamente ao pino do Arduino.
Luva ou suporte de pulso	Permitir a fixação do dispositivo sem comprometer os movimentos do usuário.
Caixa de proteção (Case)	Proteger os componentes eletrônicos e organizar a montagem.
Bateria	Permitir a alimentação portátil do dispositivo.
🧪 6. Testes e Validação

A validação do SenseWear será realizada em etapas, começando pelo funcionamento do circuito em bancada e avançando para a integração dos componentes na versão vestível.

6.1. Checklist de Desenvolvimento
Montagem do circuito MVP: integração funcional do sensor ultrassônico, LEDs de três estágios e buzzer.
Calibração das distâncias: definir e ajustar os limites exatos de cada faixa de proximidade.
Testes com diferentes superfícies: avaliar a detecção de obstáculos de diferentes tamanhos, formatos e materiais.
Implementação do alerta tátil: integrar o motor vibratório utilizando um circuito de acionamento adequado.
Testes de percepção: avaliar se as vibrações são perceptíveis e compreensíveis pelo usuário.
Desenvolvimento do suporte vestível: adaptar os componentes para utilização na mão ou no pulso.
Testes de uso contínuo: avaliar estabilidade, conforto, fixação e aquecimento dos componentes.
⚠️ 7. Limitações e Cuidados de Segurança
7.1. Limitações do Sensor Ultrassônico

O sensor HC-SR04 apresenta limitações físicas que podem interferir na identificação dos obstáculos.

Entre as principais limitações estão:

Objetos muito finos ou pequenos: podem não refletir o sinal ultrassônico de maneira suficiente.
Superfícies inclinadas: podem refletir as ondas sonoras para uma direção diferente da origem do sensor.
Materiais absorventes: superfícies como tecidos espessos podem dificultar a leitura.
Ângulo de detecção: obstáculos fora do campo de abertura do sensor podem não ser identificados.

Dessa forma, o SenseWear não garante a detecção de todos os obstáculos presentes no ambiente.

7.2. Segurança Elétrica e Mecânica

Durante a construção da versão vestível, deverão ser observados cuidados para garantir a segurança e a integridade do dispositivo.

Evitar conexões elétricas improvisadas.
Utilizar isolamento adequado nas ligações.
Não utilizar baterias danificadas.
Evitar fios expostos.
Garantir que a estrutura não apresente arestas cortantes.
Impedir que a fixação comprometa os movimentos das mãos e dos dedos.
Verificar o aquecimento dos componentes durante o funcionamento.
🚀 8. Próximas Etapas

Após a validação do MVP em bancada, o projeto avançará para o desenvolvimento da versão vestível.

As próximas etapas previstas são:

Calibrar os limites de distância do sensor ultrassônico.
Realizar testes com diferentes tipos de obstáculos.
Implementar o motor vibratório com transistor ou driver adequado.
Desenvolver uma estrutura vestível em formato de luva ou suporte de pulso.
Integrar uma bateria para alimentação portátil.
Realizar testes de conforto, estabilidade, segurança e percepção dos alertas.

Em versões futuras, o projeto poderá evoluir para o SenseWear Guardian, com funcionalidades adicionais, como detecção de remoção do dispositivo, identificação de quedas e envio de alertas SOS com localização.

Essas funcionalidades não fazem parte do escopo do MVP atual.

🔒 9. Propriedade Intelectual

Todos os direitos reservados.

Nenhuma parte deste código, documentação ou esquema de hardware pode ser copiada, modificada ou distribuída sem a autorização prévia dos autores.

💡 SenseWear — Tecnologia que aproxima.

Desenvolvendo tecnologia assistiva para promover maior autonomia, percepção ambiental e auxílio à mobilidade de pessoas com baixa visão.
