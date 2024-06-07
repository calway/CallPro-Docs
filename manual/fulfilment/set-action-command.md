### SET Action
```xml 
<Action Type="SET">
    <Variable Name="varname" Type="reference|value">1</Variable>
</Action>
```
De set actie set variabelen die in vervolg acties kunnen worden gebruikt. De variabelen krijgen de naam `VARIABLE.varname`. Standaard is een variabele een reference, dit betekend dat de waarde 1-op-1 wordt overgenomen bij later gebruik. Wanneer type="value" dan wordt de gemergde waarde meegenomen voor later gebruik.
