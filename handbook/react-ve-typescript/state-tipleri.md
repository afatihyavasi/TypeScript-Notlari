# State Tipleri

**useState** ile state oluşturduğumuzda, **initialState** değerimizin tipi state imizin otomatik olarak tipi olacaktır. Tip tanımlamak istendiği taktirde **`useState<tip>`** şeklinde tip tanımlaması yapılabilir. State tipinin tanımlaması aşağıdaki gibi olucaktır.

```typescript
const [counter, setCounter] = useState(0);
/* Tip tanimlamasi yapmadigimiz takdirte initalState
degerimiziz number tipinde oldugu icin counter tipi
number olacaktir.*/

const [name, setName] = useState<string>('');
/* useState<string> ile name statenin tipi string
olarak tanimlanmistir*/
```

 

