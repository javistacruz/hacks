---
layout: post
title: La β-reducción a prueba de tontos
author: javistacruz
category: cálculoλ
date: 2019-7-16
---
# Cálculo de proposiciones lógicas a través de un lenguaje completamente formalizado.

El Cálculo lambda sigue tres reglas:

## Hacemos cosas con cosas.
```
; Cosa:

> 1 ; número:
1
> "hola" ; palabra:
"hola"
```
Pero no hacemos nada con ellas: sólo las devolvemos como su propio valor.

Ahora, cosas que hacen cosas. Pues sumar, restar ... y esas cosas. De manera que:

LEY Nº 1 de la β-reducción: 
>LAS COSAS QUE HACEN COSAS CON COSAS SE PONEN ENTRE PARÉNTESIS: 
> cosas-que-hacen-cosas-primero cosas-con-que-se-hacen-cosas-después)
```
> (+ 1 1)
2
> (- 1 1)
0
> (- (+ 1 1) 1)
1
```
## 2.- Las cosas que hacen cosas también pueden ser descritas como cosas con las que se hacen cosas. A esto se llama λ-expresión.

¿Cómo describo un proceso y lo coloco al frente del paréntesis? por ejemplo:
```
> (autosuma 1)
What is 'autosuma'? 

; sería la suma de x

> ((x)(+ x x) 1)
What is 'x'? 
```
; Necesitamos indicar que x es una variable dentro del proceso descrito, o de lo contrario no comprende qué tipo de cosa es x. Para eso usamos la $\lambda$ en el cálculo $\lambda$.

> (λ(x)(+ x x))
#<function>
> ((λ(x)(+ x x)) 1)
2

; Podemos darle un nombre a un proceso mediante su definición:

> (define autosuma (λ(x)(+ x x)))
;; Defined autosuma
> (autosuma 1)
2
> (autosuma (autosuma 1))
4
> 
