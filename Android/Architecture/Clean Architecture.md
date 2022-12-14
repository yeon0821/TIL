# Clean Architecture?

-----

![post-thumbnail](https://velog.velcdn.com/images/galaxy/post/9e33b45e-75c6-464c-9a3b-3a1cdd7ef2c5/image.png)

## ๐ ์ค์ํ๊ฒ ์๊ฐํ๋ ๊ฒ๋ค

- ๋ด๋ถ ๋ฐ์ดํฐ์ ๋ก์ง๋ค์ ์์ชฝ์ ํฅํด์ผ ํ๋ค.
- ์์ฒญ์ ์์ชฝ์ผ๋ก ๋ค์ด์ ๋ฐ๊นฅ์ชฝ์ผ๋ก ๋๊ฐ๋ค.> ์์ฒญ ์งํ ๋ฐฉํฅ์ด ๋ณํ๋๋ ๊ฒฝ์ฐ๋ ์กด์ฌํ์ง ์๋๋ค.
- DI(Dependency Injection) : ์ธํฐํ์ด์ค์ ๋ณ๊ฒฝ์ด ์ฝ๋์ ๋ณํ๋ฅผ ์ผ์ผํค์ง ์๋๋ก ํ๋ค.
- DB, UI ๋ฑ์ ๋ฐ๋์ด๋ ํ๋ก๊ทธ๋จ ์์ฒด๋ ๋ฌธ์  ์์ด ๋์๊ฐ๋๋กํ๋ **์ธ๋ถ ์ฌํญ์ผ๋ก ์ทจ๊ธ**ํ๋ค.

## 1.  Clean Architecture๋

***\*Clean Architecture๋ Robert C Martin(Uncle Bob) ์ ์ํ ์ํํธ์จ์ด ์ค๊ณ ๋ฐฉ์์ด๋ค.\****

## 2. Clean Architecture๋ฅผ ์ฌ์ฉํ๋ ์ด์ 

- **๊ณ์ธต(Layer)๋ณ๋ก ์ญํ (๊ด์ฌ์ฌ)๋ฅผ ๋๋์ด ๋ถ๋ฆฌ**ํจ์ผ๋ก์จ **๋ค์ํ ์๊ตฌ**(๋๊ท๋ชจ ์๋ฐ์ดํธ, ์๋ก์ด ๊ธฐ๋ฅ, ๋ฒ๊ทธ์์ , ํ์คํธ, ๊ณ ๊ฐ์ ์์ฒญ)๋ฑ์ **์ ์ฐํ๊ฒ ๋์ฒ**ํ๊ธฐ ์ํด ์ฌ์ฉ
- ์ด๋ฌํ ๊ณ์ธต๊ฐ์ ์ญํ ์ ์๊ธฐ์ ์ ์์กด์ฑ ๊ท์น์ ์์์ผ ํ๋ค.

## 3. ์์กด์ฑ ๊ท์น(Dependency Rule)

- ๊ณ์ธต๋ง๋ค ๊ฒฝ๊ณ๋ฅผ ๋๋์ด์ ๊ด์ฌ์ฌ๋ฅผ ๋ถ๋ฆฌํ๊ธฐ ์ํด ์ฌ์ฉํ๋ ๊ท์น

1)**๋ชจ๋  ์์ค์ฝ๋ ์์กด์ฑ์ ๋ฐ๋์ ๋ฐ๊นฅ์ชฝ์์ ์์ชฝ์ผ๋ก, ๊ณ ์์ค ์ ์ฑ์ ํฅํด์ผ ํ๋ค**

- ์์ชฝ์ผ๋ก ๊ฐ์๋ก ๊ณ ์์ค์ ํด๋นํ๊ณ ,

  ๊ณ ์์ค๊ณผ ์ ์์ค์ ์ถ์ํ์ ์ ๋์ ๋ฐ๋ผ ๋ถ๋ฅ๋ฉ๋๋ค.

- ์ถ์ํ๊ฐ ๋ง์ด ๋์ด์์์๋ก ์์ชฝ์ ์์นํด์๊ณ  ๊ณ ์์ค์ ํด๋นํฉ๋๋ค.

2)๊ณ ์์ค์ ์๋ ๊ณ์ธต์ ์ ์์ค์ ์๋ ๊ณ์ธต์ ๋ํด ๋ชฐ๋ผ์ผ ํ๋ค.

- ์์ชฝ์ ์๋ Domain ๊ณ์ธต์ DataLayer๋ PresentationLayer์ ์์กดํ์ง ์๊ณ  ๋๋ฆฝ์ ์ผ๋ก ์คํ ๋์ด์ผ ํ๋ค๋ ๊ท์น์๋๋ค.

![img](https://velog.velcdn.com/images%2Fsery270%2Fpost%2F5537acce-99c4-4de1-8516-b3f1e7da5b85%2Fcleancoder.png)

## 4. Clean Architecture์ Layear๋ค

> ์๋ ๊ทธ๋ฆผ์ ์์์ ๋ณด์๋ Clean Architecture ๊ทธ๋ฆผ์ 90๋ ํ์ ํ ๋ชจ์ต์๋๋ค. Clean Architecture์ ๊ฐ Layer๋ค์ ์ค๋ชํ๊ธฐ ์ํด ์๋์ ๊ฐ์ด ํ์ฉ๋์์ต๋๋ค.

![img](https://velog.velcdn.com/images%2Fsery270%2Fpost%2Fbe3ae900-54b3-47c6-a4ba-03f785c7c84d%2FrotatedLayers.png)

### ๐ฆ Presentaion Layer

> ์ ๊ทธ๋ฆผ์ Presenter๋ฅผ Presenters ๋ฟ๋ง ์๋๋ผ, ViewModels๋ ํฌ๊ดํ๊ธฐ ์ํ ๋ง๋ก, Controllers๋ผ๊ณ  ๋ถ๋ฅด๊ฒ ์ต๋๋ .

- UI (*Activities & Fragments*), Controllers (*Presenters/ViewModels*) ๋ฅผ ํฌํจํฉ๋๋ค.
- Controllers (*Presenters/ViewModels*)์ 1๊ฐ ์ด์์ *Use cases*๋ฅผ ์คํํฉ๋๋ค.
- UI์ UI ๊ฐ๊ฐ์ Controllers (*Presenters/ViewModels*)์ ์ํด ์กฐ์ ๋ฉ๋๋ค.
- Presentation Layer๋ Domain Layer์ ๋์์ผ๋ก ์์กด์ฑ์ ๊ฐ์ง๋๋ค.

> Presentation Layer - - - > Domain Layer

### ๐ Domain Layear

- *Entities, Use cases, Repository Interfaces*๋ฅผ ํฌํจํฉ๋๋ค.
- *Use cases*๋ data์ 1๊ฐ ์ด์์ Repository Interfaces๋ฅผ ๊ฒฐํฉํฉ๋๋ค.
- Domain Layer๋ ๊ฐ์ฅ ์์ชฝ์ ๋ ์ด์ด์๋๋ค. ์์ ์ธ๊ธํ ์์กด์ฑ ๋ฒ์น์ ์ํด, Domain Layer๋ ๋ค๋ฅธ ๋ ์ด์ด๋ฅผ ๋์์ผ๋ก ์์กด์ฑ์ ๊ฐ์ง์ง ์์ต๋๋ค. ๋ค๋ฅธ ๋ ์ด์ด๊ฐ Domain Layer๋ฅผ ๋์์ผ๋ก ์์กด์ฑ์ ๊ฐ์ง ๋ฟ์๋๋ค.

> ์ด๋ป๊ฒ Domain Layer๋ Data Layer์ ๋ํ ์์กด์ฑ๋ ๊ฐ์ง์ง ์์ ์ ์๋์?
>
> ํ๋ง๋๋ก ๋ต๋ณํ์๋ฉด, SOLID ์์น ์ค **์์กด์ฑ ์ญ์  ๋ฒ์น**์ ํด๋นํ๋ **interface๋ฅผ ์ฌ์ฉํ ์ถ์ํ** ๋๋ถ์๋๋ค.
>
> Interface ์ถ์ํ๊ฐ ์์๋ค๋ฉด, Domain Layer์ Use cases๊ฐ Data Layer์ Repository๋ฅผ ์ฌ์ฉํด์ผํฉ๋๋ค. ์ฆ, Domain Layer - - - > Data Layer ๋ผ๋ ์์กด์ด ์๊ฒจ๋๊ฒ ๋ฉ๋๋ค.
>
> ํ์ง๋ง **Domain Layer๋ Repository๋ฅผ ์ถ์ํ์์ผ ์ฌ์ฉ**ํ๊ณ  ์๊ธฐ ๋๋ฌธ์, ์์ ๊ฐ์ ์์กด์ด ์๊ฒจ๋์ง ์๊ฒ ๋๋ ๊ฒ์๋๋ค. ์ฆ, Domain Layer๋ Data Layer์์ ๊ตฌํ๋  Repository Interfaces๋ฅผ ์ฌ์ฉํ๋ฉด์, ์์กด์ ํํผํ๊ฒ ๋ฉ๋๋ค.
>
> ์ด๊ฒ์ด ๋ฐ๋ก **Repository Interfaces๊ฐ Domain Layer์ ํฌํจ๋๋ ์ด์ **์ด์, **Repository Implementations๊ฐData Layer์ ํฌํจ๋๋ ์ด์ ** ๋ผ๊ณ  ๋ณผ ์ ์์ต๋๋ค.

> **์์กด์ฑ ์ญ์  ๋ฒ์น์ ํ๋ง๋๋ก ?**
>
> High-level modules should not depend on low-level modules, both should depend on abstractions.

### **Domain Layer**์ ํน์ง โผ๏ธ

- Domain Layer ๊ฐ์ฅ ์ค์ํ ๋ ์ด์ด ์๋๋ค โผ๏ธ ๋ฐ๋ผ์ ๋ค๋ฅธ ๋ ์ด์ด๋ค๊ณผ๋ ๋ฌ๋ฆฌ, ์ ๋ฐ๋๋ฉด ์๋ฉ๋๋ค.
  - ์ด Domain Layer์ ์ํํธ์จ์ด์ ์ค์ฌ์ด ๋๋ The business rules(Entity)๊ฐ ํฌํจ๋ฉ๋๋ค.
- Domain Layer๋ ๋ค๋ฅธ ๋ ์ด์ด๋ฅผ ๋์์ผ๋ก ์์กด์ฑ์ ๊ฐ์ง์ง ์์ต๋๋ค.
  - ์ฆ, Domain Layer๋ ํ๋ ์ ์ํฌ(Android Platform)์ ์์กด์ฑ์ ๊ฐ์ง์ง ์๊ณ , ์ค์ง ์ธ์ด ๋จ(Kotlin Module)์ ๋ํด์๋ง ์์กด์ฑ์ ๊ฐ์ต๋๋ค.
    - ๋ฐ๋ผ์, ํ๋ ์ ์ํฌ๊ฐ์ Domain Layer ์ฌ์ฌ์ฉ๋ ๊ฐ๋ฅํฉ๋๋ค.

### **Data (DataSource) Layer**

- *Repository Implementations*, 1๊ฐ ์ด์์ *Data Sources*๋ฅผ ํฌํจํฉ๋๋ค.

> Data Layer์ *Repository Implementations* Data Layer๊ฐ ๊ฐ์ง ์ฑ์ ์ค ํ๋๋ก, Domain Layer๊ฐ ์ฌ์ฉํ๋ Repository Interfaces์ ๋ํ ๊ตฌํ์ ์ด์ผ๊ธฐ ํ  ์ ์์ต๋๋ค. Domain Layer๋ Data Layer๊ฐ ๊ตฌํํด์ค๊ฑฐ๋ผ ์๊ฐํ๊ณ  Repository Interfaces๋ฅผ ์ฌ์ฉํ๊ธฐ ๋๋ฌธ์๋๋ค.

Repository๋ ๋ค๋ฅธ Data Source๋ค์ ๊ฒฐํฉ/์กฐ์ ํฉ๋๋ค.

- Repository ์ฌ๋ฌ Data Source๋ค์ ๊ฒฐํฉํ๋ ๊ฒฝ์ฐ๋ก, Local Data Source๊ณผ Remote Data Source์ ๊ฒฐํฉ์ ๋ํด ์ด์ผ๊ธฐํ  ์ ์์ต๋๋ค.

> **dataSource์ dataSourceImpl**
>
> Data Layer์ Data Source๋, ์์์ ๋ดค๋ **์์กด์ฑ ์ญ์  ๋ฒ์น**์ ์ ์ฉ์ผ๋ก, ์ถ์ํ ๋์ด interface์ Implementations์ผ๋ก ๊ตฌ์ฑ๋ฉ๋๋ค.์ฆ, Repository - - -> Data Source์ ์์กด์ ๋ํ ํํผ์๋๋ค.
>
> ํํธ, ์ด๋ ๊ฒ ์์กด์ ์์ ๋ฉด, Data Source์ ๋ณ๊ฒฝ์, Repository์ ๋ํ ์ํฅ์ ์ค์ผ ์ ์์ต๋๋ค.

Repositroy ํจํด

[[Android\] Repository Pattern](https://www.notion.so/Android-Repository-Pattern-900e3880c30c4f4f809ffe1f0852dc6a)

- Data Layer๋ Domain Layer์ ๋์์ผ๋ก ์์กด์ฑ์ ๊ฐ์ง๋๋ค.

  > Data Layer - - - > Domain Layer