# interface

**interface** sözde öğesi, tip objeleri oluşturmanın başka bir yoludur. Aşağıda fonksiyonlar ve objelerde kullanımı örneklendirilmiştir.

```typescript
interface Point {
  x: number;
  y: number;
}

function printCoord(pt: Point) {
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}

printCoord({ x: 100, y: 100 });
```

```typescript
interface Teams {
    turkey: 'fenerbahce' | 'galatasaray',
    spain: 'barcelona' | 'real-madrid'
}

let champions: Teams = {turkey: "fenerbahce", spain: "barcelona"}
```

{% hint style="info" %}
**type** ile i**nterface** aynı amaçta olsalar bile bazı farkları vardır. 

**1 -** Fonksiyon tanımlamaları farklıdır.

```typescript
interface SetPoint {
  (x: number, y: number): void;
}

type SetPoint = (x: number, y: number) => void;
```

**2 -** type ile diğer tip atamaları direk type değerine atanabilirken interface e atanamaz.

```typescript
// primitive
type Name = string;

// object
type PartialPointX = { x: number; };
type PartialPointY = { y: number; };

// union
type PartialPoint = PartialPointX | PartialPointY;

// tuple
type Data = [number, string];
```

**3 -** Extend edilme şekilleri farklıdır. Ayrıca ikisi birbirinden extend edilebilir.

#### **-Interface extends interface**

```typescript
interface PartialPointX { x: number; }
interface Point extends PartialPointX { y: number; }
```

 **-Type  extends type** 

```typescript
type PartialPointX = { x: number; };
type Point = PartialPointX & { y: number; };
```

 **-Interface extends type** 

```typescript
type PartialPointX = { x: number; };
interface Point extends PartialPointX { y: number; }
```

 **-Type extends interface**

```typescript
interface PartialPointX { x: number; }
type Point = PartialPointX & { y: number; };
```

**3 - interface** aynı isimde birden çok tanımlanabilir fakat **type** tanımlanamaz.

```typescript
interface Point { x: number; }
interface Point { y: number; }

const point: Point = { x: 1, y: 2 };
```
{% endhint %}

