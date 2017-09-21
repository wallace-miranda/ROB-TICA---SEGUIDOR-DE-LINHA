# ROB-TICA---SEGUIDOR-DE-LINHA
O presente trabalho tem como objetivo o estudo da robótica móvel em um carrinho para aplicações educacionais utilizando P.I.D para otimizar o controle do sistema.
1.	OBJETIVO
O presente trabalho tem como objetivo o estudo da robótica móvel em um carrinho para aplicações educacionais utilizando P.I.D para otimizar o controle do sistema.
Os robôs são totalmente autônomos e tem todos os sistemas embarcados, tendo assim por finalidade percorrer todo um circuito com linha preta e o fundo da pista branco no menor tempo possível.


2.	FUNDAMENTAÇÃO TEÓRICA
Segundo a ISO 10218: Um robô industrial é uma máquina para manipulação, com vários graus de liberdade, controlada automaticamente, reprogramável, multifuncional, que pode ter base fixa ou móvel para utilização em aplicações de automação industrial.
É possível associar um robô industrial ao tipo de máquina aplicada na automação flexível, sendo constituída basicamente por um manipulador mecânico acionado por atuadores a partir de um controlador, o qual opera com base em informações de movimentos programados e de sinais gerados por elementos sensores de realimentação. Tais elos permitem o correto posicionamento e a orientação da peça ou ferramenta destinada para a tarefa. [SANTOS, 2015].
Hoje em dia há várias maneiras de melhorar o desempenho e o tempo de realização de atividades na área da automação. Uma das formas bem conhecidas no ramo industrial é através do algoritmo PID (Proporcional-Integral-Derivativo). “O sucesso dos controladores PID também é reforçado pelo fato de que muitas vezes representam o componente fundamental para os sistemas de controle mais sofisticados que podem ser implementados quando a lei básica de controle não é suficiente para obter os desempenhos requeridos [VISIOLI, 2006]”.
O controlador PID e seus componentes na forma de controles PD e PI representam formas de controladores que utilizam operações de derivadas e integrais na compensação dos sistemas de controle. Em geral, pode-se considerar o projeto dos controladores dos sistemas de controle como um problema de projeto de filtros; portanto, existe uma grande quantidade de possíveis esquemas. Do ponto de vista da filtragem, o controlador PD é um filtro passa-alta, o controlador PI é um filtro passa- baixa, e o controlador PID é um filtro passa-banda ou atenua-banda, dependendo dos valores de seus parâmetros [GOLNARAGHI, 2012].
 
![image](https://user-images.githubusercontent.com/32083310/30719945-0853427e-9efc-11e7-95ea-16134c8cabf3.png)

Figura 1. Diagrama de blocos de um controlador PID em malha fechada.

A figura acima mostra um diagrama de blocos em PID de malha fechada, onde se obtêm um sinal de retorno do sistema [f(t)],  este sinal é subtraído do set point e se obtêm o erro [e(t)]. O resultado da somatória dos valores proporcionais, integrador e derivativo é [s(t)] que é a saída do controlador PID.

3.	MATERIAIS E METODOS 
Neste tópico será mostrado todos os materiais e métodos utilizados na construção do robô, facilitando assim futuras montagens.

![image](https://user-images.githubusercontent.com/32083310/30720038-5bcc1d40-9efc-11e7-858e-9276e747086d.png)

Figura 2. Robô seguidor de linha montado.

MATERIAIS	QUANTIDADE
ARDUINO UNO	1
DRIVER MOTOR PONTE H L298N	1
MODULO SENSOR INFRAVERMELHO	3
KIT CHASSI 4WD. 
Obs: incluso as 4 rodas e os 4 motores com suas reduções	1
Tabela 1. Lista de materiais.
Os testes foram feitos em uma pista feita pelo professor-orientador da turma, projetada com fundo da tela branco e linha a ser seguida pelo robô é de cor preta. Os primeiros testes do robô foram para testar seuS motores em relação a sentido de rotação e velocidade. Logo em seguida veio o teste ON/OFF e com uma velocidade bem baixa, e no decorrer dos testes fomos aumentando sua velocidade. O terceiro passo foi implementar o PID com o integral e o derivativo inexistentes, apenas modificando o Kp (controle proporcional). Após vários testes determinamos o valor de Kp e com isso começamos a procurar o valor de Ki e Kd, para fazer o robô seguia a linha de maneira mais suave e o mais rápido possível.
•	Cálculo do valor lido:
V = ( 300*E + 200*C + 100*D) / ( E + C + D );
•	Cálculo do erro:
Erro = setPoint - V;
•	Calculo dos controladores: 
P = Erro * Kp;
I = Erro * DT * Ki;
DER = ( Kd * (V - Va)) / DT;

4.	RESULTADOS E DISCURSÕES
No primeiro teste no qual não foi utilizado o PID (teste ON/OFF), foi percebido que o robô fazia movimentos bruscos e ao aumenta sua velocidade de atuação ele não conseguia seguir a linha na curva por conta de sua resposta ao processo de controle. Ao inserir o controlador Kp conseguimos notar que o robô conseguia seguir a linha na curva porem de uma maneira não tanto suave, e ao se inserir e ajustar os valores de Ki e Kd o robô conseguia fazer o circuito com pequenas oscilações.

5.	CONCLUSÕES
Concluímos que o controle usando PID é bem mais eficiente do que o ON/OFF, embora foi percebido que para esse sistema bastaria o controlador PD, pois o valor de Ki é muito baixo, chegando a ser desconsiderável.

6.	BIBLIOGRAFIA
WINDERSON, Eugênio; GORGULHO, José Hamilton Chaves; CRUZ Eduardo Cesar Alves. Robótica industrial: fundamentos, tecnologias, programação e simulação. 1ª. Ed. São Paulo. Érica, 2015.
VISIOLI, Antonio. Practical PID control. Springer, 2006.
GOLNARAGHI, M. F; KUO, Benjamin C. Sistemas de controle automático. Tradução e revisão técnica: Fernando Ribeiro da Silva.  9.Ed. Rio de Janeiro, 2012 

