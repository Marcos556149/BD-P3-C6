# BD-P3-C6
1*) A= π dni σ nota<4 exa
    alu ⨝ (π dni exa - A)
2*) BD= π codM (σ nomM='Base de Datos' ∨ nomM='Base de Datos Avanzadas' mat)
    π nomAlu (alu ⨝ (π dni, codM (σ nota ≥ 4 exa) ÷ BD))
3*) mat ⨝ (π codM σ year(fecha) = 2023 insc)
4*) π nomAlu,nomM,fecha,nota(((π dni,codM exa) ∩ (π dni,codM bol)) ⨝ alu ⨝ mat ⨝ exa)
5*) MT= π codM (σ anio = 1 ∨ anio = 2 mat)
    π dni,nomAlu (alu ⨝ (π dni,codM bol ÷ MT))
6*) A= π B,C,D ρ B ← dni, C ← codM, D ← anio (mat ⨝ insc)
    Z= A ⨯ (mat ⨝ insc)
    H= σ(B=dni ∧ C≠codM ∧ D≠anio) Z
    π dni,nomAlu (alu ⨝ H)
7*) A = rho A exa 
    π exa.dni(A ⨝(A.codM = exa.codM and A.dni = exa.dni and A.fecha != exa.fecha) exa)
    -- Otra forma es con el producto carteciano 
    π A.dni(σA.dni = exa.dni and A.codM = exa.codM and A.fecha != exa.fecha (A x exa))
8*) π nomMM,nomM ((ρ des ← despliegue,an← anio,codM ← codMc, codMM ← codM,nomMM ← nomM (mat ⨝ corre)) ⨝ mat)
9*) alternativa 1*) A= π codM ← codMc (σ codM='M2' corre)
                    alu ⨝ ((π dni σ codM = 'M2' bol) ⨝ (π dni,codM exa ÷ A))
    alternativa 2 buscando el codigo de la materia*) X= π codM σ nomM='Base de Datos' mat
                                                     A= π codM ← codMc (corre ⨝ X)
                                                     alu ⨝ ((π dni σ codM = 'M2' bol) ⨝ (π dni,codM exa ÷ A))
10*) A= π dni,codM bol
     B= π dni,codM exa
     exa ⨝ (B-A)
11*) A= π dni,codM bol
     B= π dni,codM σ nota ≥ 4 exa
     C= B-A
     D= A - (B - C)
     π nomAlu (alu ⨝ (π dni A - π dni D))
