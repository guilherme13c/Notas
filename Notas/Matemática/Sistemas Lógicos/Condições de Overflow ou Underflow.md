[[Representação de Inteiros|]]

# Soma de um bit
A estrutura do somador de um bit completo (_full bit adder_) é a seguinte:
$$\begin{equation}
\frac{
    \begin{array}[b]{r}
	  {\color{cyan}\mbox{C}_\mbox{out}} & {\color{cyan}\mbox{C}_\mbox{in}}\\
      \; & a \\
      + & b
    \end{array}
  }{
    \begin{array}[b]{r}
	  {(a\oplus b)} & {\color{orange}s}
	\end{array}
  }
\end{equation}$$
Sendo $a$, $b$ e $s$ números representados usando o [[Representação de Inteiros#Twos Complement|método do complemento de dois]], sabemos que houve overflow ou underflow quando ${\color{cyan}\mbox{C}_\mbox{in}}$ é diferente de ${\color{cyan}\mbox{C}_\mbox{out}}$.

Vale lembrar que ${\color{orange}s}=(a\oplus b)\oplus {\color{cyan}\mbox{C}_\mbox{in}}$ e ${\color{cyan}\mbox{C}_\mbox{out}}=(a\cdot b)+(a\cdot {\color{cyan}\mbox{C}_\mbox{in}})+(b\cdot {\color{cyan}\mbox{C}_\mbox{in}})$.

**_Obs._**: No circuito do ALU (Arithmetic-Logic Unit), uma das saídas é uma flag que indica se houve overflow ou underflow. Essa flag pode ser implementada usando ${\color{cyan}\mbox{C}_\mbox{in}}\oplus{\color{cyan}\mbox{C}_\mbox{out}}$.