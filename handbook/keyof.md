# keyof, typeof

### keyof

**keyof**, oluşturduğumuz tip objelerinde ki keyler ile yeni tipler oluşturmamıza olanak sağlar. Örneğin aşağıdaki gibi [interface](interfaces.md) ile tip tanımlaması yapmış olalım.

```typescript
interface Person {
    name: string
    age: number
    location: string
}
```

Ardından **keyof** ile yeni bir tip oluşturalım.

```typescript
type SomeNewType = keyof Person
```

Oluşturduğumuz tip karşılığı aşağıdaki gibidir.

```typescript
type SomeNewType: "name" | "age" | "location"
```

### typeof

Oluşturduğumuz objelerin value tiplerini elde etmemizi sağlar. Örneğin aşağıdaki gibi obje oluşturalım.

```typescript
const bmw = { name: "BMW", power: "1000hp" }
```

Ardından **typeof bmw** ile yeni bir tip ataması yapalım.

```typescript
type Car = typeof bmw;
```

Yukarıda ki **Car** tip objesinin karşılığı aşağıdaki gibidir.

```typescript
type Car = {
    name: string;
    power: string;
}
```

{% hint style="success" %}
**keyof** ve **typeof** u birlikte kullanabiliriz. Örneğin yukarıdaki örneğimizde ki gibi **bmw** objemizi oluşturalım.

```typescript
const bmw = { name: "BMW", power: "1000hp" }
```

Ardından **keyof** ve **typeof** u birlikte kullanarak yeni bir tip objesi oluşturalım.

```typescript
type CarLiteralType = keyof typeof bmw;
```

oluşturduğumuz tip objesinin karşılığı aşağıdaki gibidir.

```typescript
type CarLiteralType = "name" | "power";
```

 
{% endhint %}

 

