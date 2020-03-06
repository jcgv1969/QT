# Primera aproximación a la mecánica cuántica

La formalización matemática de la mecánica cuántica es la siguiente:

- Todo sistema físico viene modelado por un espacio de Hilbert complejo $\mathcal H$, puede que de dimensión infinita. 
- Todo estado del sistema viene dado por un vector unitario $\phi\in \mathcal H$. 
- Cada magnitud que se pueda medir sobre el estado físico viene asociada con una aplicación lineal $A$ definida en al menos un subespacio vectorial denso de $\mathcal H$ que debe ser autoadjunta (tendremos que clarificar la definición de autoadjunta en el caso de que el espacio de Hilbert sea de dimensión infinita). 
- Los valores que se obtienen al realizar una medición  deben ser  autovalores del operador $A$ asociado a la medición (o en su defecto elementos del espectro de $A$).  Por ser $A$ autoadjunto los elementos del espectro son números reales y no complejos, así que las mediciones son números reales. 
- Si $A$ representa un cierto observable físico y $\phi$ es un estado que pertenece al dominio de $A$ entonces la esperanza de la medida viene dada por el producto escalar

$$
\langle \phi, A\phi\rangle.
$$

En resumen, esta es la formalización matemática de la mecánica cuántica.

## Operadores y adjuntos de operadores: introducción.

Sea $\mathcal H$ un espacio de Hilbert complejo. Siempre asumiremos que es un espacio separable (existe un subconjunto denso y numerable). Seguiremos la convención de la literatura física en la que se considera que el producto escalar de $\mathcal H$ es lineal en la segunda componente 
$$
\langle \phi,\lambda\psi\rangle=\lambda \langle \phi,\psi\rangle
$$
para todo $\lambda \in \mathbb C$, y antilineal en la primera componente
$$
\langle \lambda\phi, \psi\rangle=\overline\lambda \langle \phi,\psi\rangle
$$
para todo $\lambda \in\mathbb C$.

**Definición.** Una aplicación lineal  $A:\mathcal H\to \mathcal H$ , también llamada operador,  es **acotada** si existe una constante $C>0$ tal que
$$
\|A\phi\|\leq C\|\phi\|
$$
para todo $\phi\in \mathcal H$. La menor constante $C$ que cumpla lo anterior se llama norma del operador $A$ y se denota por $\|A\|$.
**Comentario.** Si $A$ es un operador definido sobre un subespacio vectorial de $\mathcal H$, digamos $A: D(A)\subset \mathcal H\to \mathcal H$, entonces también se puede hablar de  la norma de $A$ sobre $D(A)$ y del concepto de acotado sobre $A$.

**Teorema.**  Sea $V_1$ un espacio vectorial normado y sea $V_2$ un espacio de Banach.  Sea $ W$ un subespacio vectorial denso de $V_1$ y $T : V_1\to V_2$ una aplicación lineal acotada. Entonces existe un único operador lineal acotado $\tilde T:V_1\to V_2$ tal que  $\tilde T|_W=T$. Más aún, la norma de $\tilde T$ es la misma que la norma de $T$.
**Demostración.** AF.$\blacksquare$ 
**Comentario.** Si $A$ es un operador definido sobre un subespacio vectorial $A: D(A)\subset \mathcal H\to \mathcal H$, y $A$ es acotado en $D(A)$, entonces podemos extender $A$ a un operador $\widetilde A$ sobre el cierre $\overline{D(A)}$ que además tiene la misma norma que el operador $A$ sobre $D(A)$. Así que si tenemos un operador acotado, por extensión, siempre podemos considerarlo por defecto definido sobre un subespacio vectorial cerrado de $\mathcal H$. 

La existencia del operador adjunto para un operador acotado es fácil de justificar.

**Teorema.** Dado $A: \mathcal H\to \mathcal H$ operador acotado, existe $A^*:\mathcal H\to \mathcal H$ operador acotado,  llamado operador adjunto de $A$, que cumple lo siguiente 
$$
\langle \phi, A\psi\rangle =\langle A^* \phi, \psi\rangle
$$
para todo par de vectores $\phi,\psi\in \mathcal H$.
**Demostración.** Fijemos $\phi\in \mathcal H$. La aplicación $\psi\to \langle \phi,A\psi\rangle$ es lineal y acotada. Por el teorema de representación de Riesz, debe existir un vector en $\mathcal H$, al que vamos a llamar $\eta$ , tal que
$$
\langle \phi,A\psi\rangle=\langle \eta,\psi\rangle
$$
Este procedimiento establece una aplicación lineal de $\mathcal H$ en $\mathcal H$:  la que a cada $\phi\in H$ le asigna  $\eta\in H$.   Llamo $\eta=A^*\phi$. Entonces $A^*:H\to H$ es lineal (fácil de comprobar) y además es acotada porque para cualquier $\phi$ de norma unidad
$$
	\begin{aligned} 
	\|A^*\phi\|&=\|\eta\|\\
	&=\sup\{|\langle \eta, \psi\rangle|:  \|\psi\|=1\}\\
	&=\sup\{|\langle  \phi, A\psi \rangle|:  \|\psi\|=1\}\\
	&\leq   \|A\| 
	\end{aligned} 
$$
Luego $\|A^*\|\leq \|A\|$. Esto demuestra que $A^*$ es un operador acotado. $\blacksquare$ 


**Definición.**  $A$ operador acotado es **autoadjunto** si $A=A^*$, esto es, si ocurre que
$$
 \langle A\phi,\psi\rangle =\langle \phi, A\psi\rangle
$$
para todo par de vectores $\phi,\psi\in\mathcal H$.

**Comentario**. Si $A:\mathcal H\to \mathcal H$ es lineal y $ \langle A\phi,\psi\rangle =\langle \phi, A\psi\rangle$ para todo par de vectores en $\mathcal H$  entonces $A$ es acotado inmediatamente (es un teorema de AF). 

**Definición.**  Un operador $A$ no acotado sobre $\mathcal H$ es una aplicación lineal $A:D(A)\subset H\to H$ definida sobre un subespacio vectorial denso en $\mathcal H$  que no es acotada sobre su dominio de definición.

Dado un operador no acotado $A$ queremos de definir el operador adjunto $A^*$. Hay una dificultad si queremos  usar la misma idea que usamos en el teorema para operadores acotados porque si fijamos $\phi\in \mathcal H$,  resulta que la aplicación lineal a valores complejos $\psi\to \langle \phi, A\psi\rangle$ no es necesariamente acotada y por ello no define un elemento del espacio dual de $\mathcal H$ por lo que no podemos llamar al teorema de representación de Riesz para definir quien es $A^*\phi$ .

**Definición.**  Sea $A$ no acotado. Definimos $A^*$ del siguiente modo. Primero, diremos que $\phi$ pertenece al dominio de $A^*$ si la aplicación lineal $\psi\to \langle \phi, A\psi\rangle$ es acotada en $D(A)$, que recordemos es denso en $\mathcal H$. Para tales $\phi$ definimos entonces  $A^*\phi$ como el único $\eta\in H$ tal que $\langle \eta,\psi\rangle= \langle \phi, A\psi\rangle$ para todo $\psi\in D(A)$. Si el funcional $\psi\to \langle \phi, A\psi\rangle$ es acotado en $D(A)$ sabemos que existe  una única extensión lineal a todo $\mathcal H$  que además conserva la norma. El teorema de Riesz garantiza entonces la existencia y unicidad de $\eta$ para cada $\phi\in D(A^*)$. De este modo $A^*$ es una aplicación lineal definida sobre su propio dominio $D(A^*)$, formado por aquellos $\phi$ para los que la aplicación lineal $\psi\to \langle \phi, A\psi\rangle$ es acotada en $D(A)$. 

**Definición.**  Sea $A$ un operador no acotado. Diremos que es **simétrico** si $\langle \phi, A\psi\rangle = \langle A \phi, \psi\rangle$
para todo par de vectores $\phi,\psi\in D(A)$. 

**Definición.**  Sea $A$ un operador no acotado. Diremos que es **autoadjunto** si $D(A)=D(A^*)$ y $A=A^*$ sobre el dominio común.

**Definición.** $A$ es **esencialmente autoadjunto** si la clausura en el espacio producto $\mathcal H\times \mathcal H$ del grafo de $A$ es el grafo de un operador autoadjunto.

**Comentario.** Cualquier autoadjunto o esencialmente autoadjunto es simétrico, pero no al revés. Si $A$ es simétrico entonces $D(A^*)\supset D(A)$ y $A^*$ coincide con $A$ sobre $D(A)$. La razón por la que un operador simétrico $A$ puede no ser  autoadjunto es porque $D(A^*)$ sea estríctamente mayor que $D(A)$. 


Aunque la noción de simétrico es la más natural, es la noción de autoadjunto la correcta en el sentido de que la teoría espectral de operadores es aplicable a los autoadjuntos pero no a todos los simétricos. Si $A$ es esencialmente autoadjunto entonces basta tomar clausura a su rango y obtener un operador autoadjunto al que aplicar el teorema espectral.


En general es sencillo demostrar que los operadores que aparecen en mecánica cuántica son simétricos en ciertos dominios naturales, pero demostrar que son esencialmente autoadjuntos es más difícil. 

**Teorema.**  Sea $A$ operador simétrico sobre $\mathcal H$. 

1. Para todo $\psi\in D(A)$ el producto $\langle \psi, A\psi\rangle$ es un número real. Más general, si $A^k \psi\in D(A)$ para $k=1,\dots, m$ entonces $\langle \psi, A^m\psi\rangle$ es un número real.
2. Sea $\lambda\in\mathbb C$ tal que $A\psi=\lambda \psi$ para algún $\psi\in D(A)$ no nulo. Entonces $\lambda\in \mathbb R$.

**Demostración.** Observa que para cualesquiera dos vectores $\langle \phi,\psi\rangle=\overline{\langle \psi,\phi\rangle}$ luego  $\langle \psi,A\psi\rangle=\overline {\langle A\psi,\psi\rangle}$.  Para (2) observa que $\langle \psi,A\psi\rangle=\langle \psi,\lambda\psi\rangle =\lambda \|\psi\|^2$. $\blacksquare$

**Comentario. ** Los productos escalares  $\langle \psi, A\psi\rangle $ representan en mecánica cuántica la media de las mediciones de observable asociado al operador $A$ cuando el sistema se encuentra en el estado $\psi$ . Los autovalores de $A$ son  los posibles resultados de la medición.

## Posición y momento

Una partícula en $\mathbb R$ es un sistema físico. Tiene asociado el espacio de Hilbert $L^2(\mathbb R)$. Un estado de la partícula tiene asignado de manera biunívoca un vector unitario del espacio de Hilbert no nulo que llamamos función de onda.  Una función de onda es pues una  $\phi:\mathbb R\to\mathbb C$ de cuadrado integrable Lebesgue. Dependerá del tiempo, pero aquí lo vemos en un instante fijo. 

En mecánica cuántica se asume que la probabilidad de que la partícula se encuentre dentro del boreliano $E\subset \mathbb R$ viene dada por la integral
$$
\int_E |\phi(x)|^2dx
$$

Como $\phi$ se elige como vector unitario tenemos una medida de probabilidad. 

También se asume que el valor esperado de la posición es el valor de la siguiente integral:
$$
\mathbb E(x)=\int_{\mathbb R} x|\phi(x)|^2dx
$$
En general, el momento de orden $n$ de la posición viene dado por la integral:
$$
\mathbb E(x^m)=\int_{\mathbb R} x^m|\phi(x)|^2dx
$$
para todo $m\in\mathbb N$. La idea clave es representar todo lo anterior en términos de operadores. En este caso, el operador que se va a asociar al observable posición de la partícula es el operador  $$X:D(X)\subset \mathcal L^2(\mathbb R)\to \mathcal L^2(\mathbb R)$$
definido por la fórmula  $$X(\phi)(x)=x\phi(x).$$ Es el operador multiplicación por $x$ que queda bien definido en un cierto subespacio vectorial denso de $\mathcal L^2(\mathbb R)$. Recordemos que el producto escalar en $L^2(\mathbb R)$ es
$$
\langle \phi,\psi\rangle =\int_{\mathbb R} \overline{\phi(x)}\psi(x)dx

$$
así que es claro que
$$
\mathbb E(x)=\langle \phi,X\phi\rangle.
$$
La notación  para el valor medio esperado de la posición en el estado $\phi$ será $\langle X\rangle_\phi$
También se tiene que
$$
\mathbb E(x^m)=\langle \phi,X^m\phi\rangle=\langle X^m\rangle_\phi
$$


A tiempo fijado la función de ondas $\phi$ solo depende de la variable $x$. La función $|\phi(x)|^2$ codifica las probabilidades de la posición. Pero ¿cómo se codifica el momento?  El momento viene codificado en las oscilaciones de $\phi$.  La hipótesis de de Broglie: si la función de ondas de una partícula tiene frecuencia espacial $k$, entonces el momento de la partícula es $k\hbar$ siendo $\hbar$ la constante de Planck. 

La hipótesis supone que una función de ondas del tipo $\phi(x)=\exp(ikx)$ representa una partícula de momento $p=\hbar k$  (frecuencia en el sentido angular,  los ciclos por unidad de distancia vendrían dados por $\nu=k/2\pi$). 

Pero las funciones  $\phi(x)=\exp(ikx)$  no son de cuadrado integrable Lebesgue en $\mathbb R$.  Para evitar problemas consideremos una situación más sencilla en la que la partícula se mueve en la circunferencia unidad y no en $\mathbb R$. El espacio de Hilbert asociado es ahora $L^2([0,2\pi])$.

 Consideremos entonces funciones de ondas $\psi:[0,2\pi]\to\mathbb C$  tales que $\displaystyle \int_0^{2\pi}|\psi(x)|^2dx=1$. Ahora la función normalizada $\exp(ikx)/\sqrt{2\pi}$ sí que representa una partícula de momento $p=\hbar k$ según de Broglie.  El momento de la partícula está perfectamente definido en este estado, no es aleatorio. Si la función de ondas de la partícula es $\exp(ikx)/\sqrt{2\pi}$ entonces una medición del movimiento de la partícula debe dar como momento el valor $\hbar k$ con probabilidad $1$. 

Sabemos que el sistema $\{\exp(ikx)/\sqrt{2\pi}\}_{k\in\mathbb Z}$ es un sistema ortonormal completo en $L^2([0,2\pi])$. Así, cualquier $\psi$ vector normalizado en el espacio de Hilbert puede ser representado así
$$
\psi=\sum_{k=-\infty}^\infty a_k \exp(ikx)/\sqrt{2\pi}
$$
donde los coeficientes $(a_k)$ son números complejos tales que
$$
\|\psi\|^2=\sum_{k=-\infty}^\infty |a_k|^2=1
$$
Para una partícula en el estado $\psi$ el momento no está definido. Lo que se dice en mecánica cuántica  (es un axioma)  es que el momento será $\hbar k$ con probabilidad $|a_k|^2$. La esperanza será
$$
\mathbb E(p)=\sum_{k=-\infty}^\infty \hbar k |a_k|^2
$$
Los momentos generalizados serán 
$$
\mathbb E(p^m)=\sum_{k=-\infty}^\infty (\hbar k)^m |a_k|^2
$$
para $m\in\mathbb N$. 

Necesitamos un operador momento $P$ que codifique todo lo anterior en un producto escalar. Definimos
$$
P(\exp(ikx))=\hbar k \exp(ikx)
$$
para cada entero $k$. Ya lo tengo definido sobre los elementos de la base del espacio $\mathcal L^2([0,2\pi]$.  Luego extendemos por linealidad a toda $\displaystyle \psi=\sum_{k=-\infty}^\infty a_k \exp(ikx)/\sqrt{2\pi}$ para la que la sucesión $(\hbar k a_k)$ sea una sucesión de cuadrado integrable. Tenemos así un operador definido en un cierto  subespacio vectorial denso de $L^2([0,2\pi])$ que cumple claramente que
$$
\mathbb E(p)=\langle \psi, P\psi\rangle
$$
para todo $\psi$ en el dominio de definición de  $P$. Más aún, también
$$
\mathbb E(p^m)=\langle \psi, P^m\psi\rangle
$$
siempre que $\psi$ sea tal que $P^k\psi$ esté en el dominio de $P$ para todo $k=1,\dots,m-1$.

En el caso de la recta real podemos ahora conjeturar que el operador $P$ debe venir definido por
$$
P\phi(x)=-i\hbar \phi'(x)
$$
Este operador desde luego cumpliría que
$$
P(\exp(ikx))=\hbar k\exp(ikx)
$$
con lo que captura la idea de que la función de onda $\exp(ikx)$ tiene momento $\hbar k$. Sin embargo, la función de ondas $\exp(ikx)$ no es de cuadrado integrable en $\mathbb R$. Pero, aún así, la transformada de Fourier nos permite escribir cualquier función de onda de cuadrado integrable en $\mathbb R$ como una superposición de ondas del tipo $\exp(ikx)$.

Recordemos que si $\psi:\mathbb R\to\mathbb C$   de cuadrado integrable es lo suficientemente buena (por ejemplo, es integrable Lebesgue en $\mathbb R$), podemos escribir
$$
\psi(x)=\frac{1}{\sqrt{2\pi}}\int_{\mathbb R} \exp(ikx)\hat{\psi}(k)dx
$$
donde $\hat \psi(k)$ es la transformada de Fourier
$$
\hat \psi(k)=\frac{1}{\sqrt{2\pi}}\int_{\mathbb R} \exp(-ikx)\psi(x)dx.
$$
El teorema de Plancherel nos dice que la transformada de Fourier se puede extender a una transformación unitaria y biyectiva de $\mathcal L^2(\mathbb R)$ sobre sí mismo. Para $  \psi\in \mathcal L^2(\mathbb R)$  vector unitario entonces $\hat \psi$ es un vector unitario en $\mathcal  L^2(\mathbb R)$. Si tenemos en cuenta lo que ocurre en el caso de la circunferencia, es natural pensar que $|\hat \psi(k)|^2$ es la densidad de $p/\hbar$. Es lo análogo al papel jugado por  $|\psi(x)|^2$ para  la densidad de la posición. 

**Teorema.**  Sea $\displaystyle P=-i\hbar \frac{\partial}{\partial x}$. Para $\psi\in D(P)\subset \mathcal L^2(\mathbb R)$ unitario, se tiene que
$$
\langle \psi, P\psi\rangle=\int_{\mathbb R} (\hbar  k)|\hat\psi(k)|^2dk
$$
Más aún, para $\psi$ lo suficientemente bueno
$$
\langle \psi, P^m\psi\rangle=\int_{\mathbb R} (\hbar  k)^m|\hat\psi(k)|^2dk
$$
para todo natural $m$.

**Demostración.** Asumiremos que $\psi$ es una función de Schwartz. Entonces, por las propiedades de la transformada de Fourier 
$$
\langle \psi,P\psi\rangle=\langle \mathcal F \psi,\mathcal F (P\psi)\rangle=\int_{\mathbb R} \overline{\hat \psi(k)}k\hbar\hat\psi(k)dk=\int_{\mathbb R} \hbar k|\hat\psi(k)|^2dk
$$
Los teoremas sobre la transformada de Fourier se estudian en la asignatura Análisis de Fourier.



En resumen, una partícula confinada a $\mathbb R$ tiene como espacio de Hilbert asociado $\mathcal L^2(\mathbb R)$ y la posición y el momento vienen dados por los operadores
$$
X\phi(x)=x\phi(x)
$$
y 
$$
P\phi(x)=-i\hbar \phi'(x)
$$


Son dos operadores no acotados que se pueden definir en subespacios vectoriales densos de $\mathcal L^2(\mathbb R)$. Los dominios  $D(X)$ y $D(P)$ serán determinados más adelante. La intersección de ambos es un subespacio vectorial denso en cualquier caso. Se puede hablar de los operadores composición $XP$ y $PX$ sin problemas en ese dominio común. Ahora no nos paramos en precisar los subespacios vectoriales densos sobre los que se pueden definir sin problemas. Los operados posición y momento no conmutan y cumplen la siguiente relación.

**Teorema.**  $XP-PX=i\hbar I$ siendo $I$ el  operador identidad en $\mathcal L^2(\mathbb R)$. 
**Demostración.** Es muy sencilla de comprobar.	 

**Teorema.** Los operadores $P$ y $X$ son simétricos en ciertos subespacios vectoriales densos en $\mathcal L^2(\mathbb R)$
**Demostración.** Para el operador $X$ consideramos el espacio vectorial formado por aquellas funciones $\phi$ de $\mathcal L^2(\mathbb R)$ tales que $x\phi(x)$ también pertenecen a $\mathcal L^2(\mathbb R)$. Es inmediato probar en este subespacio vectorial el operador $X$ es simétrico.

Para el operador momento hay que considerar el subespacio de $\mathcal L^2(\mathbb R)$ formado por aquellas $\phi$ diferenciables tales que $\phi'(x)$ también pertenece a $\mathcal L^2(\mathbb R)$. Tener en cuenta en este caso que $(\overline \phi)'(x)=\overline{\phi'(x)}$.  $\blacksquare$ 

**Comentario.** Los operadores $X$ y $P$  son esencialmente autoadjuntos en ciertos dominios naturales. Esto será probado más adelante.

## Los axiomas de la mecánica cuántica: operadores y mediciones

La lista de axiomas de la mecánica cuántica que ya adelantamos a principios del artículo:

- Axioma 1. Cada estado del sistema viene representado por un vector no nulo de un espacio de Hilbert complejo y separable $\mathcal  H$.    Dos vectores linealmente dependientes y no nulos representan el mismo estado.
- Axioma 2. Cada función real $f$ sobre el espacio de fases clásico (observable) tiene asociado un operador autoadjunto $A=\hat f$ (acotado o no acotado) sobre el espacio de Hilbert.
- Axioma 3. Si el estado cuántico viene dado por el vector normalizado $\psi$ y $A$ es el operador asociado a un observable $f$, los momentos generalizados de la distribución de probabilidad de las mediciones de $f$ satisfacen $\mathbb E(A^m)=\langle \psi,A^m\psi\rangle$. En particular la esperanza de las mediciones es $\langle \psi,A\psi\rangle$. En caso de que el vector de estado no esté normalizado entonces la esperanza vendrá dada por el cociente $\displaystyle \frac{\langle \psi,A\psi\rangle}{\langle \psi,\psi\rangle}$.

El axioma 3 soporta la idea de que dos estados linealmente dependientes no nulos representan el mismo estado del sistema.

Usaremos la notación $\langle A\rangle_\psi=\langle \psi,A\psi\rangle$ para representar la esperanza de las mediciones del observable aasociado al operador $A$. 

**Teorema.** Supongamos que el sistema está en el estado normalizado $\psi$ y que $A\psi=\lambda \psi$ para cierto número real $\lambda$ ( $\psi$ es un vector propio de $A$ con autovalor $\lambda$). Entonces $\langle A^m\rangle_\psi=\lambda^m$. La única distribución de probabilidad consistente con esta condición es la que asigna peso $1$ a $\lambda$ y  $0$ al resto.

**Demostración.**  La primera parte inmediata. La única medida de probabilidad con esos momentos es la medida de Dirac concentrada en $\lambda$.$\blacksquare$ 

**Comentario.** Si el estado del sistema es un vector propio de $A$ la medición no es aleatoria, siempre se mide el valor $\lambda$ del autovalor asociado. 

Supongamos que $A$ es tal existe una base ortonormal de $\mathcal  H$ formada por vectores propios de $A$, digamos $(e_j)_{j=1}^\infty$, todos ellos asociados a autovalores distintos para ponernos en un caso muy simple. Supongamos que $\psi$ es un vector normalizado que representa el estado del sistema. Para todo vector de $\mathcal  H$  podemos encontrar coeficientes complejos $a_j$ tales que
$$
\psi=\sum_{j=1}^\infty a_je_j
$$
serie convergente en $\mathcal H$. Además $\displaystyle 1=\|\psi\|^2=\sum_{j=1}^\infty |a_j|^2$.

En ese caso, la esperanza de la medición en el estado $\psi$ es
$$
\langle A\rangle_\psi=\langle \psi,A\psi\rangle=\sum_{j=1}^\infty |a_j|^2\lambda_j.
$$
Los momentos generalizados son:
$$
\langle A^m\rangle_\psi=\sum_{j=1}^\infty |a_j|^2\lambda_j^m
$$
La distribución de probabilidad  discreta que asigna peso $|a_j|^2$ al valor $\lambda_j$ para cada $j$ es una candidata a ser la distribución que modela el proceso. La probabilidad de medir un valor distinto de los $\lambda_j$ es nula en esta distribución de probabilidad. Rigurosamente solo podemos estar seguros de que es ella si podemos asegurar que es la única distribución de probabilidad con los momentos fijados (ver la asignatura de Análisis Funcional). Si no podemos aplicar ese teorema no tendremos garantía de la unicidad. La distribución que hemos mostrado aquí parece la más natural y asumimos que es la válida.

**Comentario.**  El desarrollo anterior puede extenderse al caso en el que algunos de los autovalores sean degenerados, esto es, que su correspondiente espacio de vectores propios tenga dimensión mayor que $1$. Para cada autovalor $\lambda$, la probabilidad de obtener $\lambda$ en la medición se calcula con la siguiente suma
$$
\sum_{j\in E_\lambda} |a_j|^2
$$
donde $E_\lambda$ es la colección formada por aquellos índices $j$ tales que $e_j$ es un vector propio asociado al autovalor $\lambda$. 

**Comentario.** Para cualquier operador autoadjunto $A$ (ya sea acotado o no) el teorema espectral que estudiaremos en próximas secciones nos dirá que podemos encontrar tal base ortonormal de $\mathcal H$ formada por vectores propios de $A$ o en su defecto se puede encontrar algún análogo continuo que permite hacer los cálculos de probabilidad de las mediciones. Así, para cada $A$ autoadjunto y estado $\psi$ tendremos asignada una medida de probabilidad $\mu_\psi^A$ sobre $\mathbb R$ de tal modo que la probabilidad de que la medición caiga en un boreliano $E\subset \mathbb R$ vendrá dada por $\mu_\psi^A(E)$. 



Proseguimos con la lista de axiomas

- Axioma 4. Supongamos que inicialmente el sistema está en el estado $\psi$ y se realiza una medición del observable asociado al operador $A$. Si el resultado de la medición es $\lambda$ entonces inmediatamente después de la medición el estado del sistema debe ser un vector propio asociado al autovalor $\lambda$, esto es, debe ser un vector $\psi'$ tal que $A\psi'=\lambda \psi'$. El paso de $\psi$ a $\psi'$ se llama colapso de la función de ondas. 

**Comentario.** Por este axioma 4, si medimos un observable e inmediatamente (de forma instantánea) lo volvemos a medir, con probabilidad $1$ obtendremos el mismo valor.

**Definición.** Si $A$ es un operador autoadjunto sobre $\mathcal H$ y $\psi\in \mathcal H$ es un vector unitario, definimos la varianza de $A$ en el estado $\psi$ mediante la fórmula
$$
	(\Delta_\psi(A))^2=\langle (A-\langle A\rangle_\psi I)^2\rangle_\psi
$$
o equivalentemente
$$
	(\Delta_\psi(A))^2=\langle A^2\rangle_\psi-(\langle A\rangle_\psi)^2
$$
**Definición.**  $\Delta_\phi A$ es la incertidumbre de $A$ en el estado $\psi$.

Dado un operador autoadjunto $A$ es posible encontrar $\psi\in \mathcal H$  unitario para el que $\Delta_\psi (A)$ sea tan pequeño como se quiera. Sin embargo, probaremos  que si $A$ y $B$ son dos operadores autoadjuntos que no conmutan entonces es imposible encontrar un vector unitario $\psi$ para el que el producto de las incertidumbres $\Delta_\psi (A)\Delta_\psi (B)$ sea tan pequeño como se quiera. Este resultado se llama principio de incertidumbre de Heisemberg. Por ejemplo, tratándose de los operadores posición $X$ y momento $P$, el principio de incertidumbre   dice que
$$
\Delta_\phi (X) \Delta_\phi (P)\geq \frac{\hbar}{2}
$$
para cualquier $\phi\in \mathcal H$  para el que estén definidas las incertidumbres de $X$ y de $P$.



**Teorema.**  Sean $A,B,C$ tres operadores autoadjuntos tales que $[A,B]=iC$. Entonces

1. Para cada $t\in\mathbb R$ tenemos $(A-itB)^*(A-itB)=A^2+tC+t^2C^2$.
2. Para todo vector normalizado $\psi$ se tiene que $\|(A-itB)\psi\|^2=\mathbb E_\psi(A^2)+t\mathbb E_\phi(C)+t^2\mathbb E_\psi(B^2)$. 
3. Para cada $\psi$ tenemos que $\mathbb E_\psi(A^2)\mathbb E_\psi(B^2)\geq \frac{1}{4}\mathbb E_\psi(C)^2$.
4. La igualdad en el apartado anterior solo se produce si y solo si existe un número real $t$ tal que $(A-itB)\psi=0$ o equivalentemente que  $( A^2+t^2B^2)\psi=-tC\psi$ 

Demostración. 		 

**Teorema**. [Principio de incertidumbre de Heisenberg] La varianza de la posición y el momento están relacionada por la desigualdad $\displaystyle \Delta_\psi(P)\Delta_\psi(X)\geq \frac{\hbar}{2}.$ La cota inferior se alcanza si y solo si $\displaystyle \psi(x)=\exp\left(\frac{t}{2\hbar}(x-\mu)^2+\alpha\right)$. 

Demostración. 

%paginas 84,85 de hannabuss

**Definición.**  Los estados $\psi$ para los que $\Delta_\psi(P)\Delta_\psi(X)=\hbar/2$ se llaman estado de mínima incertidumbre.

## Evolución temporal en mecánica cuántica

​	Hasta ahora hemos hablado de función de ondas de forma estática. Es el momento de ver cómo evoluciona la función de ondas con el paso del tiempo. En el caso clásico la evolución viene dada por el hamiltoniano (energía) del sistema físico. En el contexto de la mecánica cuántica debe existir un operador autoadjunto   $\hat H$  que esté asociado al hamiltoniano. 

La definición del operador momento vino motivada por la hipótesis de de Broglie $p=k\hbar$ siendo $k$ la frecuencia espacial de la función de ondas. La evolución temporal va a venir motivada por la relación entre energía y la frecuencia temporal de la función de ondas $E=\hbar\omega$.  Esta relación fue propuesta por Planck en su modelo de radiación de cuerpo negro. 



Supongamos que el sistema en un instante $t=0$ se encuentra en el estado $\psi_0$, que es un vector de estado con una energía bien definida. Esto significa que $\psi_0$ debe ser un vector propio del operador  $\hat H$ asociado a cierto autovalor $E$ de $\hat H$.	

En el instante $t$ la función de ondas será
$$
\psi(t)=e^{-i\omega t}\psi_0=e^{-iEt/\hbar}\psi_0
$$
Esta evolución temporal se puede codificar con una ecuación diferencial
$$
\frac{d\psi}{dt}=-\frac{iE}{\hbar}\psi=\frac{E}{i\hbar}\psi
$$
Esta ecuación diferencial controla la evolución de la función de ondas cuando el sistema parte de un estado propio con energía bien definida, esto es un vector propio de $\hat H$ asociado a cierto autovalor $E$. Una forma natural de generalizar esta expresión es reconocer que $E\psi$ es $\hat H\psi$ pues $\psi(t)$ es un múltiplo no nulo de $\psi_0$ y por ello vector propio de $\hat H$ también. Si reemplazamos $E$ por $\hat H$ en la ecuación de evolución anterior podemos establecer el siguiente axioma.

- Axioma 5. La evolución temporal de la ecuación de ondas viene dada por la ecuación de Schrödinger

$$
\frac{d\psi}{dt}=\frac{1}{i\hbar}\hat H\psi
$$

​    donde $\hat H$ es el operador asociado al hamiltoniano del sistema.

 **Teorema.**  Sea $\psi(t)$ solución de la ecuación de Schrödinger y $A$ operador autoadjunto. Asumiendo las condiciones que hagan falta en el dominio de $A$ se tiene que
$$
\frac{d}{dt}\langle A \rangle_{\psi(t)}=\langle\frac{1}{i\hbar}[A,\hat H]\rangle_{\psi(t)}.
$$
**Demostración.** Mucho cuidado si no son operadores acotados.

 

**Comentario.**  Una consecuencia directa del teorema anterior es que si el operador $A$ conmuta con el hamiltoniano $\hat H$ entonces la media de las mediciones de $A$ no varía con el tiempo. 

**Definición.**  Si $A$ conmuta con $\hat H$ diremos que $A$ es una cantidad conservada del sistema. 

La aplicación $(A,B)\to (1/i\hbar)[A,B]$ juega un papel muy parecido al que juega el producto corchete de Poisson en el caso clásico.

**Teorema.** Propiedades del conmutador:

1.  $[A,B+\alpha C]=[A,B]+\alpha [A,C]$.
2. $[A,B]=-[B,A]$
3. $[A,BC]=[A,B]\, C+ B\, [A,C]$.
4.  $[A,[B,C]]+[B,[C,A]]+[C,[BA,B]]=0.$

**Demostración.**  



Si $A$ y $B$ son autoadjuntos y acotados es claro que $(1/i\hbar)[A,B]$ es acotado autoadjunto. Si $A$ y $B$ son autoadjuntos pèro  no acotados entonces  $(1/i\hbar)[A,B]$ será autoadjunto si se imponen ciertas condiciones sobre los dominios de $A$ y $B$.

**Teorema.** Si $\psi(t)$ y $\phi(t)$ son soluciones a la ecuación de Schrodinger entonces el producto escalar $\langle \psi(t),\phi(t)\rangle$ es constante. En particular $\|\psi(t)\|$ es constante.

**Demostración.** Hay que usar la regla de derivación del producto escalar y la ecuación de Schrodinger. $\blacksquare$ 

La ecuación de Schrodinger es un ejemplo típico de ecuación de la forma
$$
\frac{dv}{dt}=Av
$$
donde $A$ es un operador lineal sobre el espacio de Hilbert $\mathcal  H$.   En el caso particular de la ecuación de Schrodinger $A=-(i/\hbar) \hat H$. 

 

 Si el espacio de Hilbert es de dimensión finita el operador $A$ viene representado por una matriz de orden digamos $n\times n$ y ese tipo de ecuaciones se resuelve en las asignaturas elementales de ecuaciones diferenciales poniendo
$$
v(t)=e^{tA}v_0
$$
donde la matriz exponencial $e^{tA}$ se define mediante una serie de potencias convergente y $v_0=v(0)$ es la condición inicial. Si la matriz $A$ es diagonalizable entonces la exponencial se puede calcular usando una base de vectores propios de $A$. 

En la ecuación de Schrodinger reemplazamos $\mathbb C^n$ por un espacio de Hilbert complejo $\mathcal H$ que puede ser de dimensión infinita y la matriz $A$ por el operador autoadjunto $-(i/\hbar)\hat H$.

 

 \textbf{Hipótesis.} Supongamos que $\hbar H$ es un operador autoadjunto sobre $H$. Si existe alguna forma razonable de definir el operador exponencial $e^{-it\hat H/\hbar}$ entonces la ecuación de Schodinger se resuelve así

 $$\psi(t)=e^{-it\hat H/\hbar}\psi_0$$

 	 