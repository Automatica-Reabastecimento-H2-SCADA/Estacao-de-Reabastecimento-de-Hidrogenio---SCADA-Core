# Mapeamento de Variáveis de Processo para Proposições Lógicas

Na automação industrial (norma ISA-5.1), instrumentos e atuadores emitem e recebem sinais discretos (binários: $0$ = Falso / $1$ = Verdadeiro), permitindo a tradução de condições físicas de campo em variáveis lógicas estruturadas para o processamento em sistemas de controle e intertravamento.

![Estação de reabastecimento](/etapa-01-logica/projeto2.png)


 
 
## Setor 200: Condicionamento (Pré-resfriamento)
 
| Tag Instrumento | Tipo de Dispositivo    | Variável Física                  | Proposição Lógica | Estado 1                                                       |
| ---------------- | ----------------------- | ---------------------------------- | ------------------ | ------------------------------------------------------------------ |
| **TT-201**       | Transmissor Temp.       | Temp. de Saída do Pré-resfriador   | $t\_{2,1}$              | Temperatura de pré-resfriamento adequada ($T \leq -40^\circ\text{C}$) |
| **PT-201**       | Transmissor Pressão     | Pressão do Buffer de Condicionamento| $p\_{2,1}$             | Pressão do buffer dentro da faixa de operação                      |
| **M-201**        | Contator do Motor       | Unidade de Refrigeração (Chiller)  | $m\_{2,1}$              | Chiller LIGADO e operacional  
| **XV-201**        | Válvula Corte Rápido      | valvula de entrada do chiller  | $v\_{2,1}$              | Válvula de segurança de entrada ABERTA                                       |
 
## Setor 300: Dispensador e Transferência para o Veículo
 
| Tag Instrumento | Tipo de Dispositivo    | Variável Física                              | Proposição Lógica | Estado 1                                                        |
| ---------------- | ----------------------- | ---------------------------------------------- | ------------------ | -------------------------------------------------------------------- |
| **HS-301**       | Chave Manual            | Comando de Início de Abastecimento             | $h\_{3,1}$              | Botão de início de abastecimento acionado pelo operador              |
| **COM-301**      | Comunicação IR          | Protocolo de Comunicação com o Veículo (J2799) | $c\_{3,1}$              | Comunicação estabelecida com o veículo                               |
| **BV-301**       | Válvula de Ruptura      | Acoplamento do Bico Dispensador (Breakaway)    | $bv\_{3,1}$             | Acoplamento do bico conectado e íntegro                              |
| **XV-301**       | Válvula Solenoide       | Alimentação do Bico Dispensador                | $v\_{3,1}$              | Válvula de dispensação ABERTA                                        |
| **PT-301**       | Transmissor Pressão     | Pressão no Bico (Nozzle)                       | $p\_{3,1}$              | Pressão de enchimento atinge o setpoint do veículo ($P \approx 700\text{ bar}$) |
| **TT-301**       | Transmissor Temp.       | Temp. no Ponto de Recepção do Veículo          | $t\_{3,1}$              | Temperatura no ponto de recepção excede o limite ($T > 85^\circ\text{C}$) |
| **AT-301**       | Detector de Gás H₂      | Concentração de H₂ na Área do Dispensador      | $g\_{3,1}$              | Vazamento de hidrogênio detectado na área de abastecimento           |
