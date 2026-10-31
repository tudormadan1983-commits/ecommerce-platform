# Impact E-Commerce — Backend (template)

Proiectul vostru de backend pentru Anul 2. Structura, Maven și Spring Boot sunt gata;
codul îl scrieți voi, lecție cu lecție.

## Cerințe
- Java 17 sau mai nou
- IntelliJ IDEA
- Docker Desktop (de la Lecția 2, pentru baza de date)

## Pornire
1. În IntelliJ: *File → Open* → alegeți fișierul `pom.xml` → *Open as Project*.
2. Așteptați să se descarce dependențele (bara de jos). Dacă apar erori roșii la
   `springframework`, deschideți panoul **Maven** din dreapta și apăsați *Reload*.
3. Deschideți `src/main/java/md/impact/ecommerce/EcommerceApplication.java` și apăsați ▶.
4. Aplicația pornește pe **http://localhost:8080**.
   Documentația API: **http://localhost:8080/swagger-ui.html**

## Unde scrieți codul
```
src/main/java/md/impact/ecommerce/
  EcommerceApplication.java   pornirea aplicației (nu o modificați)
  controllers/    rutele HTTP          (PracticeController, ProductController...)
  services/       logica aplicației    (ProductService, AuthService...)
  repositories/   accesul la baza de date
  entities/       clasele pentru tabele (Product, Category, User...)
  dtos/           ce intră și iese prin API
  exceptions/     erorile și răspunsurile JSON de eroare
  security/       token-urile JWT
  config/         configurări (securitate, CORS, cache)
  pricing/        reguli de preț și reduceri
```
Fiecare folder are un `package-info.java` care spune ce se pune în el.

## Lecția 1 — prima rută
Creați în `controllers/` un `PracticeController` pe `/api/practice`:

| Verb | Răspuns (`text/plain`) |
|------|------------------------|
| `GET`    | `api initialised` |
| `POST`   | `youve posted: {corp}` |
| `PUT`    | `your update is : {corp}` |
| `PATCH`  | `you have updated the : {corp}` |
| `DELETE` | `youve deleted : {corp}` |

Verificați cu frontend-ul (dublu-click pe `index.html`): bara de progres trebuie să ajungă la `5 / 5`.

## De la Lecția 2 — baza de date
1. Porniți Docker Desktop.
2. În terminalul din IntelliJ: `docker compose up`
   (pornește PostgreSQL cu tabelele și datele de test, plus Redis).
3. În `pom.xml` decomentați blocul **Lecția 2**, apoi Maven → *Reload*.

Conturi de test: `admin@impact.md` / `admin123` (ADMIN), `user@impact.md` / `user123` (USER).

Conexiunea la baza de date (pentru DBeaver sau IntelliJ):
host `localhost`, port `5432`, baza `e-commerce`, user `postgres`, parola `2302`.
