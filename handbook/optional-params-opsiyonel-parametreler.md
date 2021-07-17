# Optional Params \(Opsiyonel Parametreler\)

**TypeScript** ile oluşturduğumuz objelerde \([type](type.md), [interface](interfaces.md)\) veya fonksiyonlarda parametreleri opsiyonel olduğunu belirtmek için `parametreIsmı?:` şeklinde `?` ni kullanabiliriz.

Aşağıda opsiyonel parametre kullanımı örneklerini inceleyebilirsiniz.

```typescript
const fullName = (firstName: string, lastName?: string) => {
    console.log(firstName + lastName)
}

fullName('osman')
```

```typescript
type User = (name: string, surname?: string) => void;

const getFullName: User = (name, surname) => {
    console.log(`${name} ${surname}`)
}

getFullName('osman')

```



