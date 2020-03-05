### Interfaces

```typescript
interface IQueen {
  name: string;
  quote: string;
}

function quoteFunc(queen: IQueen): string {
  return `${queen.name} said ${queen.quote}`
}

let bianca = {
  name: 'Bianca Del Rio',
  quote: `I will show you versatility when Santino 
  wins a sewing competition and Visage wears a fucking turtle neck!`
}
quoteFunc(bianca)
```