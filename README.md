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
