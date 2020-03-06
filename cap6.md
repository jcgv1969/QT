# Necesidad de la teoría espectral en el contexto de la mecánica cuántica.

## Dificultades en el caso de tratar con espacios de Hilbert de dimensión infinita.

Supongamos que  $A=(a_{kj})$ es una  matriz **autoadjunta** de orden $n\times n$ con entradas complejas, esto es, $a_{jk}=\overline{a_{kj}}$ para todo par de índices $k,j.$  Por un resultado que vamos a dar por conocido de álgebra lineal se sabe que existe una base ortonormal de $\mathbb C^n$ formada por vectores propios de la matriz $A$ asociados a autovalores reales. 

 Este resultado se puede reescribir en términos de espacios de Hilbert de dimensión finita sobre el cuerpo de los números complejos: si $\mathcal H$ es un espacio de Hilbert complejo de dimensión finita y $A:\mathcal H\to \mathcal H$ es una aplicación lineal y  autoadjunta en el sentido de que 
$$
\langle \phi,A\psi\rangle=\langle A\phi,\psi\rangle
$$
para todo par de vectores $\phi,\psi\in \mathcal H$,  entonces existe una base ortonormal de $\mathcal  H$ formada por vectores propios de $A$ asociados a autovalores reales. 

Recordemos que en mecánica cuántica todo observable  sobre un sistema físico  debe venir asociado a un operador (aplicación lineal) autoadjunto definido sobre un cierto espacio de Hilbert (o al menos sobre un subespacio vectorial denso de un espacio de Hilbert). Cuando este  espacio de Hilbert es de dimensión finita, el hecho explicado en  el párrafo anterior, que existe una base ortonormal del espacio de Hilbert $\mathcal H$ formada por vectores propios del operador)  es fundamental para poder resolver de manera efectiva las ecuaciones y calcular las cantidades de interés de la mecánica cuántica. 
 

Pero no todo sistema físico lleva asociado un espacio de Hilbert de dimensión finita. Si queremos tratar con rigor el caso en el que el espacio de Hilbert sea de dimensión infinita sería perfecto que el teorema de existencia de bases ortonormales formadas por vectores propios del observable fuese cierto, porque en ese caso podríamos repetir  paso por paso todos los métodos válidos para el caso finito-dimensional.  Pero no es así. Pongamos un ejemplo, pongamos que  $\mathcal H=\mathcal L^2([0,1])$, el espacio de Hilbert formado por las (clases de) funciones medibles Lebesgue  $f:[0,1]\to\mathbb C$  tales que la función |f|^2 es integrable Lebesgue en en intervalo [0,1]. Este es un ejemplo típico de espacio de Hilbert complejo de dimensión infinita que aparece de forma natural en mecánica cuántica para modelizar ciertas clases de sistemas.

 Consideremos la aplicación lineal (operador)
$$
A:\mathcal L^2([0,1])\to \mathcal L^2([0,1])
$$
definida por la fórmula siguiente 
$$
A\phi(x)=x\phi(x).
$$
Es fácil probar que $A$ es una aplicación lineal (inmediato de comprobar)  que está bien definido, esto es, que si $\phi\in L^2([0,1])$ entonces $A\phi$ también está en $\mathcal L^2([0,1])$. También es fácil de comprobar que $A$ es autoadjunto:
$$
\langle \phi,A\psi\rangle=\int_0^1 \overline \phi(x)x\psi(x)dx=\int_0^1 \overline {x\phi(x)}\psi(x)dx=\langle A\phi,\psi\rangle
$$
para cualquier par de funciones $\phi,\psi\in\mathcal L^2([0,1])$.

Más aún, $A$ es un operador **acotado**. La definición de operador acotado es la siguiente: sea $T:\mathcal H\to \mathcal H$ un operador (aplicación lineal) definido sobre $\mathcal H$. Se dice  que es acotado si existe una constante   $C>0$ tal que $\|A\phi\|\leq C\|\phi\|$ para todo $\phi\in H$. Eso quiere decir que la imagen de la bola unidad de $\mathcal H$ por $T$ es un conjunto acotado de $\mathcal H$. La menor constante $C$ que se puede poner se llama norma del operador. Lo veremos con detalle. La definición de acotado se puede dar para operadores que no estén definidos en todo $\mathcal H$, sino en un subespacio vectorial de $\mathcal H$: la definición es evidente.

Volvamos a nuestro ejemplo. El operador $A\phi(x)=x\phi(x)$ es autoadjunto y acotado y sin embargo no tiene vectores propios. En efecto, si queremos que se cumpla una ecuación del tipo
$$
A\phi=\lambda \phi
$$
para un complejo $\lambda\in \mathbb C$ y un vector $\phi$ en $\mathcal L^2([0,1])$ inmediatamente deducimos que eso solo puede ocurrir si la función $\phi$ se anula en casi todo punto de $[0,1]$ y por ello es el vector nulo en $\mathcal L^2([0,1])$. Así que nos podemos olvidar de que exista una base del espacio de Hilbert $\mathcal H=\mathcal L^2([0,1])$  formada por vectores propios de $A$ porque es que no existen vectores propios. Sin embargo,  en  mecánica cuántica se dice que $A$ tiene "vectores propios"  y que tales "vectores propios"  son las deltas de Dirac $\delta(x-\lambda)$.

Formalmente, la función $\delta(x)$ es la función que vale $0$ para todo $x\neq 0 $ y $\infty$ si $x=0$.  La función $\delta(x-\lambda)$ sería la que vale $0$ si $x\neq \delta$ y $\infty$ si $x=\delta$. Observa que cualquier delta de Dirac es la función nula en cualquiera de los  espacios de Hilbert clásicos  $\mathcal L^2([a,b])$ o en $\mathcal L^2(\mathbb R)$ porque cualquier función delta de Dirac es igual en casi todo a la función nula. 

No obstante, las deltas de Dirac son "vectores propios" de $A$ porque efectivamente cumplen la ecuación formal
$$
x\delta(x-\lambda)=\lambda \delta(x-\lambda)
$$
para todo $0\leq x\leq 1$. Así que en mecánica cuántica, $A$ sí que tiene autovalores (de hecho, cualquier $0\leq \lambda \leq 1$ lo es) y vectores propios. Aunque estos "vectores propios"  no se pueden visualizar en $\mathcal H=\mathcal L^2([0,1])$ (porque si los visualizamos ahí son todos iguales al vector nulo) se espera que de alguna forma estén relacionados con una base ortonormal de $L^2([0,1])$ y que esto pueda ser formalizado matemáticamente de alguna forma. Estudiaremos esto con detalle más adelante. 

En cualquier caso el ejemplo del operador $A\phi(x)=x\phi(x)$  es importante porque prueba que en dimensión infinita no existe un teorema espectral análogo al caso finito dimensional para operadores lineales autoadjuntos, ni siquiera si $A$ es un operador acotado.

Pero no todo son noticias negativas, aún siendo $\mathcal H$ de dimensión infinita, si el operador $A:\mathcal H\to \mathcal H $ es autoadjunto y **compacto** sí que existe la deseada base ortonormal de $\mathcal H$ formada por vectores propios de $A$, imitando así el comportamiento en el caso finito dimensional. La condición de ser operador compacto es mucho más fuerte que la condición de ser acotado. Un operador $T:\mathcal H\to \mathcal H$ es compacto si el cierre del conjunto $\{T\phi: \phi\leq 1\}$ es un conjunto compacto en $\mathcal H$. Cualquier operador compacto es acotado por supuesto, puesto que todo compacto de $\mathcal H$ es un conjunto acotado, pero no cualquier acotado es compacto. Es una condición muy fuerte sobre el operador. Si $\mathcal H$ es de dimensión finita sí que es cierto que todo operador acotado es compacto. 

Aunque este resultado  nos pueda parecer  prometedor desgraciadamente los operadores interesantes en mecánica cuántica no suelen ser  compactos, y la realidad es que  muchos ni siquiera son  acotados.
Un ejemplo claro de esto que decimos es el que llamaremos operador posición $X$ que está definido sobre cierto subespacio vectorial  de  $\mathcal L^2(\mathbb R)$  del siguiente modo:
$$
X(\phi)(x)=x\phi(x)
$$
La misma definición que la del anterior operador $A$, pero esta vez sobre el espacio de Hilbert $\mathcal L^2(\mathbb R)$. Observa que $X$ no está definido sobre todo el espacio de Hilbert $\mathcal L^2(\mathbb R)$.  Por ejemplo, $f(x)=1/(1+|x|)$ es un vector de $\mathcal L^2(\mathbb R)$ pero $xf(x)$ no. Vamos a llamar $D(X)\subset \mathcal L^2([0,1])$ a dicho subespacio vectorial donde actúa de forma natural $X$. Lo escribiremos así:
$$
X:D(X)\subset L^2([0,1])\to L^2([0,1])
$$
Para ver que $X$ no es un operador acotado sobre su dominio natural $D(X)$ vamos a construir una sucesión de funciones $\phi_n\in D(X)$ tales que $\|\phi_n\|=1$ y sin embargo $\|X\phi_n\|\to+\infty$. Esto probará que $X$ no es un operador acotado (en esas condiciones es imposible  que exista $C\geq0 $ cumpliendo que $\|X\phi\|\leq C \|\phi\|$ para todo $\phi\in D(X)$).
Tomemos $\phi_n=\chi_{[n,n+1]}$, la función característica del intervalo $[n,n+1]$. Clatamente
$$
\|\phi_n\|=\left(\int_n^{n+1}1\, dx\right)^{1/2}=1
$$
Por otro lado
$$
\|X\phi_n\|=\left(\int_{n}^{n+1} x^2dx\right)^{1/2}\geq n
$$

Hemos probado que $X$ , el operador posición, clave en todo el desarrollo de la mecánica cuántica, no es un operador acotado. Lo que sí se puede demostrar de forma muy sencilla es que 
$$
\langle \psi, X\phi\rangle=\langle X\psi,\phi\rangle
$$
para cualquier par de vectores $\phi,\psi\in D(X)$.

En análisis funcional se demuestra que si $A:\mathcal H\to \mathcal H$ es un operador definido en todo el espacio de Hilbert $\mathcal H$  cumple que $\langle \phi,A\psi\rangle=\langle A \phi,\psi\rangle$ para todo par $\phi,\psi\in \mathcal H$, entonces automáticamente $A$ es un operador acotado. Por lo tanto, si un operador no es acotado  y cumple que $\langle \phi,A\psi\rangle=\langle A \phi,\psi\rangle$ para todo par de vectores de su dominio, este operador no puede estar definido sobre todo $\mathcal  H$. Este es el caso que se plantea en mecánica cuántica la mayor parte de las veces.

Diremos entonces que $A$ es un  operador no acotado sobre el espacio de Hilbert $\mathcal H$  si $A$  una aplicación lineal $A:D(A)\subset H\to H$, definida sobre un subespacio vectorial **denso** en $\mathcal H$. Lo de denso es importante para poder hablar del operador adjunto como veremos más adelante. Recordemos que $M\subset \mathcal H$ es un conjunto denso en $\mathcal H$ si $\overline M =H$, o de otro modo, que dado $\phi\in \mathcal H$  y dado $\varepsilon>0$ cualesquiera, existe $\psi \in  M$ tal que $\|\phi-\psi\|<\varepsilon.$

La noción de autoadjunto en el contexto de los operadores no acotados  es  complicada, desde luego no es tan inmediata como en el caso acotado. En principio hay una definición  muy natural que es la que a todo el mundo se le ocurriría: $A:D(A)\subset \mathcal H\to \mathcal H$ definido sobre un subespacio denso de $\mathcal H$ es autoadjunto si cumple que $\langle \phi,A\psi\rangle=\langle A \phi,\psi\rangle$ para todo par de vectores  $\phi,\psi$ en el dominio de definición $D(A)$. El operador posición $X$ definido sobre $\mathcal L^2(\mathbb R)$ cumple esta condición. Sin embargo, esta condición no es lo suficientemente buena para garantizar que un teorema espectral adecuado sea aplicable al operador $A$. Es necesario considerar otra definición mucho más artifical.  El procedimiento adecuado es el siguiente:

- Se define el operador adjunto de $A$, notado   por $A^*$, que  no necesariamente tendrá el mismo dominio de definición que $A$. Para poder definir $A^*$ bien es necesario imponer que $A$ esté definido sobre un conjunto denso de $\mathcal H$, de lo contrario no hay forma. Por eso se le pide en la propia definición a los operadores que estén definidos sobre subespacios vectoriales densos en $\mathcal H$. 
- Un operador no acotado $A$ se dirá **autoadjunto** si ocurre que $A=A^*$, y no solo en el sentido de que coincidan como aplicaciones en la intersección de los dominios, sino en el sentido de que los dominios sean iguales y que  ambas aplicaciones coincidan sobre el dominio común.



## Objetivos de la teoría espectral en el contexto de la mecánica cuántica

Vamos a explicar   cuales son los objetivos que buscamos con el desarrollo de una teoría espectral aplicada a la mecánica cuántica. Sabemos, por ejemplo, que la ecuación de Schrödinger dependiente del tiempo se resuelve formalmente poniendo
$$
\psi(t)=\exp(-it\hat H/\hbar)\psi_0
$$
siendo $\hat H$ el operador Hamiltoniano y $\psi_0$   el estado inicial del sistema. Cuando este operador $\hat H$ es no acotado no es posible expresar el operador exponencial $\exp(-it\hat H/\hbar)$ como una serie de potencias (algo que sí es posible hacer  si es acotado de una forma relativamente directa). Pero bueno, aunque $\hat H$ no sea acotado, si dispusiéramos de una base ortonormal del espacio de Hilbert $\mathcal H$ formada por vectores propios de $\hat H$, digamos $(e_k)_{k=1}^\infty$, con cada $e_k$ vector propio asociado a un autovalor $\lambda_k$, entonces podríamos definir el operador exponencial $ \exp(-it\hat H/\hbar)$ del siguiente modo. Primero digo como va a funcionar sobre los elementos de la base:
$$
\exp(-it\hat H/\hbar)(e_k)= e^{-it\lambda_k/\hbar}e_k
$$
para todo $k=1,2,\dots$. Pues bien, entonces sobre cualquier $\phi\in \mathcal H$  podemos definir 
$$
\exp(-it \hat H/\hbar)\phi=\sum_{k=1}^\infty c_ke^{-it\lambda_k/\hbar}e_k
$$
siendo $\displaystyle \phi=\sum_k c_ke_k$ la expresión del vector $\phi$ respecto de la base $(e_k) $.  

Se puede probar que  $\exp(-it\hat H/\hbar)(e_k)$ queda perfectamente definido sobre todo $\mathcal H$  y es además acotado. 

Es para los casos en los que no tengamos una base ortonormal  de autovectores de $\hat{H}$ donde necesitamos una teoría espectral que nos proporcione un cálculo funcional de operadores; un formalismo que permita aplicar funciones a operadores. Esta es la primera meta de la teoría espectral en el contexto de la mecánica cuántica. 

En segundo lugar, también queremos que la teoría espectral nos proporcione una distribución de  probabilidad para las mediciones del observable asociado a un operador autoadjunto. Vamos a explicar esto con un ejemplo.  Supongamos que tenemos un observable asociado a un operador $A$ autoadjunto para el que es posible encontrar  una base ortonormal de $\mathcal H$  formada por  vectores propios de $A$. Vamos a ponernos en el caso más simple posible, en el que además no existan autovalores degenerados. Si tenemos esto entonces  tenemos una forma natural de medir probabilidades. Sea $E$ un boreliano cualquiera de $\mathbb R$. Sea $V_E\subset \mathcal H$  el subespacio vectorial cerrado generado por los vectores propios asociados a autovalores contenidos en $E$, esto es, por todos aquellos vectores $e_j\in\mathcal H$ tales que $\lambda_j\in E$. Sea $P_E:\mathcal H\to \mathcal H$ la proyección ortogonal asociada al subespacio vectorial cerrado $V_E$ que viene definida del siguiente modo
$$
P_E(\phi)=\sum_{\lambda_j\in E} c_j e_j
$$
para $\displaystyle \phi=\sum c_je_j$  escrito como combinación de la base de $\mathcal H$.
Para cualquier vector de estado $\phi\in \mathcal H$, de norma unidad, la probabilidad de medir un autovalor que pertenezca al conjunto $E$ viene dada por la fórmula
$$
\mathbb P_\phi(A\in E)=\langle \phi,P_E\phi\rangle
$$
Así que si tenemos un vector de estado unitario (de norma $1$)  $\phi$ que se descompone así
$$
\phi=\sum c_je_j
$$
en términos de la base de vectores propios, entonces la probabilidad de observar el valor $\lambda_j$ es igual a
$$
\mathbb P_\phi(A\in\{\lambda_j\})=\mathbb P_\phi(A=\lambda_j)= |c_j|^2
$$
porque en ese caso la proyección $P_{\{\lambda_j\}}$ es justo la proyección sobre el vector $e_j$.

Observa que entonces el producto escalar $\langle \phi, A\phi\rangle$ realmente es la esperanza de la distribución que toma los valores $\lambda_j$ con probabilidad $|c_j|^2$:
$$
\langle \phi,A\phi\rangle =\sum_j \overline c_j c_j \lambda_j=\sum_j \lambda_j |c_j|^2.
$$
En los casos en los que el operador $A$ no tenga asociada una base ortonormal de vectores propios lo que  queremos es que el teorema espectral nos proporcione una colección de proyecciones $\{P_E: E  \text{ boreliano}\}$ que nos permitan calcular las probabilidades deseadas $\mathbb P_\phi(A\in E)$. Tales operadores de proyección $P_E$ se llamarán proyecciones espectrales y los subespacios vectoriales asociados $V_E$ se llamarán subespacios espectrales. De alguna forma, los subespacios espectrales $V_E$ podrán ser pensados como los subespacios vectoriales generados por esos "vectores propio" de los que se habla en mecánica cuántica. 

Estos son los dos objetivos fundamentales que perseguimos en este contexto con la teoría espectral. 

Recuperemos ahora el operador posición $X:D(X)\subset \mathcal L^2(\mathbb R)\to \mathcal L^2(\mathbb R)$. Sabemos que $X$ no tiene autovalores ni vectores propios, claro. También sabemos que $X$ no es acotado.  Podemos pensar que los objetos $\delta(x-\lambda)$ de algún modo juegan el papel de vectores propios para el caso del operador $X$. Cuando apliquemos el correspondiente teorema espectral a este operador $X$ obtendremos  que  los subespacios $V_E$ en este caso van a ser los subespacios vectoriales formados por las funciones soportadas en $E$ (que en cierto modo son como el subespacio vectorial generado por las funciones deltas de Dirac $\delta(x-\lambda)$ con $\lambda \in E$). Para cada conjunto de Borel $E\subset \mathbb R$ la proyección $P_E$ será el operador
$$
P_E(\phi)=\phi\chi_E
$$
para todo $\phi\in \mathcal L^2(\mathbb R)$. Entonces, si $\phi$ es un vector unitario (un posible estado del  sistema):
$$
\begin{aligned} 
\mathbb P_\phi(X\in E)&=\langle \phi,P_E \phi\rangle\\
&=\langle \phi,\chi_E \phi\rangle\\
&=\int_E|\phi(x)|^2dx
\end{aligned} 
$$
que es la fórmula que cabía esperar pues sabemos que si el sistema se encuentra en el estado $\phi$ entonces  $|\phi|^2$ es la distribución de probabilidad de la posición.

Para el operador posición $X$ el cálculo funcional también será extremadamente simple. Si $f(x)$ es una función medible Borel y acotada entonces  $f(X)$ será el operador multiplicación
$$
f(X)\phi(x)=f(x)\phi(x)
$$
En particular, el operador asociado a $f(x)=e^{iax}$, con $a\in\mathbb R$,  es el operador definido por
$$
e^{iaX}(\phi)(x)=e^{iax}\phi(x).
$$
Así de sencillo.