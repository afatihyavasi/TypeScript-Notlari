# useRef

Herhangi bir elemanımıza ref verdiğimiz zaman, **useRef** hook una elemanın tipini belirtmeliyiz. Ayrıca **initialValue** değerini de vermeliyiz. React projelerimizi JavaScript ile yazdığımızda **initialValue** değerini boş bıraktığımızda hata almıyorduk fakat TypeScript hata vericektir.

```typescript
const inputRef = useRef<HTMLInputElement>(null);

 <input type={'password'} ref={inputRef} placeholder={'Password'}/>
```

 



