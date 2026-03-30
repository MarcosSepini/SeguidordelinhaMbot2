<h2 align="left">Seguidor de linha Kp (Mbot2)</h2>

###

<h6 align="left">O mBot2 é uma plataforma robótica avançada de última geração, projetada para educação e competições. Diferente de robôs educacionais básicos, ele é alimentado pela CyberPi, um microcontrolador de alto desempenho que suporta processamento multitarefa e Python nativo.<br><br>Diferencial Técnico: Ele utiliza motores com encoders ópticos, que permitem um controle de velocidade e posição extremamente preciso, ignorando variações de carga ou bateria fraca.<br><br>Conectividade: O uso do módulo mbuild permite a comunicação via barramento industrial, facilitando a integração de sensores complexos como o Quad RGB.</h6>

###

<h2 align="left">Tipo de Seguidor de Linha (Controle Proporcional)</h2>

###

<h6 align="left">O código implementa um Seguidor de Linha Proporcional (P). Diferente de um seguidor "on-off" (que apenas vira bruscamente para a esquerda ou direita), este modelo calcula a magnitude do erro.Lógica Matemática: O desvio da linha (offset) é multiplicado pelo ganho $K_p$.Suavidade: Se o robô está apenas um pouco fora da linha, a correção é leve. Se o desvio é grande, a correção é intensa. Isso resulta em um movimento fluido, reduzindo o desgaste mecânico e aumentando a velocidade média nas curvas.</h6>

###

<h2 align="left">Etapas de Execução do Algoritmo</h2>

###

<h6 align="left">O fluxo de trabalho do código pode ser segmentado em quatro estágios cíclicos:Entrada (Sensing): O sensor quad_rgb lê a posição da linha e retorna um valor numérico (erro).<br><br>Processamento (Calculus): O algoritmo aplica a fórmula $(base\_power \pm (kp \times erro))$ para determinar a nova velocidade.Atuação (Actuation): O comando mbot2.drive_power envia os sinais de PWM (modulação por largura de pulso) para os motores.<br><br>Feedback: O loop while True reinicia o processo instantaneamente, corrigindo a trajetória em milissegundos.</h6>

###

<h2 align="left">Bibliotecas e Módulos</h2>

###

<h6 align="left">O sucesso deste código depende da orquestração de quatro bibliotecas fundamentais:<br><br>cyberpi: Gerencia o sistema operacional do robô e o hardware principal.<br><br>event: Responsável por monitorar as interações do usuário (como o pressionamento do botão 'B').<br><br>mbuild: A camada de comunicação que traduz os dados brutos do sensor Quad RGB em valores de offset utilizáveis.<br><br>mbot2: A biblioteca de abstração de hardware que controla os drivers de motor e a locomoção do chassi.</h6>

###
