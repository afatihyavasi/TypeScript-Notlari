# Type Assertion

Bazen **TypeScript**'in bilemeyeceği bir değerin türü hakkında bilgi sahibi oluruz. Örneğin,

```typescript
let code: any = 123; 
```

 şeklinde bir tanımlama yaptığımızda **code** değerimiz **any** tipine sahiptir. **code** değişkenimize number bir değer verdik fakat tip olarak number olduğunu belirtmedik. Bu durumda editörümüz bize **number** metodlarını önermeyecektir.

Bu durumda **type assertion** özelliği devreye giriyor. Aşağıdaki iki yöntemle **type assertion** yapabiliriz.

```typescript
<tip> degiskenIsmi
degiskenIsmi as tip
```

 Örneğimize uygulaması aşağıdaki gibidir.

```typescript
(<number>code).toExponential();
(code as number).toExponential()
```

 

