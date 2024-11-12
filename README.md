## Single Threading va Multi Threading

- **Single Threading** – Bir vaqtning o'zida faqat bitta jarayon yoki ilovaga bitta ishni bajarishga imkon beradi.
- **Multi Threading** – Bir vaqtning o'zida bir nechta ishlarni bajarishga imkon beradi, ya'ni bir nechta oqimlarda ishlarni parallel bajarish uchun ishlatiladi.

## Synxron va Asinxron Dasturlash

- **Synxron Dasturlash** – Kod yuqoridan pastga qarab ketma-ket ishlaydi va bir kod tugagunicha keyingisi boshlanmaydi.
- **Asinxron Dasturlash** – Boshqa vazifalarni bajarish davomida ma'lum operatsiyalarni kutish yoki bekor qilmasdan ishlashga imkon beradi. Bu asosan vaqti ko'p talab qiladigan vazifalar uchun foydali (masalan, tarmoq so'rovlari).

## JavaScript Event Loop

Event loop – bu JavaScriptning asinxron kodni boshqaradigan mexanizmi. U yordamida `call stack` va `callback queue` boshqariladi, ya'ni sinxron kod va asinxron kod o'z ketma-ketligida bajariladi.

## Microtask Queue va Task Queue

- **Task Queue (yoki Macrotask Queue)** – Bu setTimeout, setInterval kabi kodlarni o'z ichiga oladi.
- **Microtask Queue** – Promise'lar va boshqa microtasklarni boshqaradi. Microtasklar har doim Tasklardan oldin bajariladi.

# Kodning Ishlash Tartibi

```javascript
console.log("1");

setTimeout(function t2() {
  console.log("2");
}, 100);

setTimeout(function t2() {
  console.log("0");
}, 0);

Promise.resolve().then(function t3() {
  console.log("3");
});

fetch("https://google.com").then(() => {
  console.log("google");
});

console.log("4");
```

# Chiqish

`1`, `4`, `3`, `0`, `google`, `2`
