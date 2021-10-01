## <a name="variable"></a>Как объявить переменную в TypeScript?

Вы можете создавать переменные тремя способами: `var`, `let` и `const`.

`var` - это старый стиль объявления переменных.

`let` - это способ объявления переменных в TypeScript по умолчанию. По сравнению с `var` `let` уменьшает количество ошибок времени компиляции и повышает читаемость кода.

```typescript
let num: number = 1;
```

`const` создает постоянную переменную, значение которой не может измениться. Он использует те же правила области видимости, что и let, и помогает снизить общую сложность программы.

```typescript
const num: number = 100;
```

## <a name="constructor"></a>Как вызвать конструктор базового класса из дочернего класса в TypeScript?

Вы можете использовать функцию `super()` для вызова конструктора базового класса.

```typescript
class Animal {
	name: string;
	constructor(theName: string) {
		this.name = theName;
	}
	move(distanceInMeters: number = 0) {
		console.log(`${this.name} moved ${distanceInMeters}m.`);
	}
}

class Snake extends Animal {
	constructor(name: string) {
		super(name);
	}
	move(distanceInMeters = 5) {
		console.log("Slithering...");
		super.move(distanceInMeters);
	}
}
```