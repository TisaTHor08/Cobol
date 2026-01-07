##VARIABLES

le chiffre XX avant la variable definit sa hierarchie, on peut donc faire des sous variable, sachant qu'on increment de 05 a chaque fois.

les prefixs de variables sont:
WS-	Working Storage (variables internes)
FD-	File Description
LK-	Linkage Section
LS-	Local Storage

PIC est une description, elle dit au compilateur de reserver l'espace decrit ensuite (9(3)) dans la mémoire, c'est "comme" une fonction "reserver"

les types de variables:
X(y) -> string de y caractères (les caractères manquant sont comblé avec des espaces)
9(y) -> int de y digit (comblé par des 0 par la gauche: 7 -> 007 si y=3)
S9(y) -> int positif ou negatif (avec un signe definit)
9(y)V9(z) -> le V définit une virgule implicite de z digit après la virgule
A(y) -> seulement alphabétique
Z(y) -> equivalent au 9 mais sans les 0 précédents

##OPERATEUR

ADD [] TO 
SUBTRACT [] FROM
MULTIPLY [] BY
DIVIDE [] BY

ajouter GIVING [] permet de ne pas modifier la seconde variable mais de seulement appliquer le resultat a la 3e

sinon en générale utiliser COMPUTE:
COMPUTE WS-RES = (WS-A + WS-B) / 2.

Attention a l'overflow (si 9(2) alors on ne peut pas depasser 99)

N'utiliser les verbes que si opération simple et nécéssaire a pointer du doigt, pour dire "LA on ajoute X"
