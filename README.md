# TP – Spring : IoC et injection de dépendances

## Outils utilisés

- IntelliJ IDEA
- Java 21
- Maven
- Spring Framework 6.1.2 (`spring-context`)
- JUnit 4.13.2

## 1. Injection avec `@Autowired`

![Autowired](Screenshots/Image1springdi.png)

Spring injecte automatiquement `DaoImpl` (100.0). Résultat : **200.0**.

## 2. Injection avec `@Qualifier("dao2")`

![Qualifier](Screenshots/Image2springdi.png)

Spring injecte `DaoImpl2` (150.0). Résultat : **300.0**.

## 3. Profil `dev`

![Profil dev](Screenshots/Image3springdi.png)

Seul `DaoImpl2` est actif : « Version de développement ». Résultat : **300.0**.

## 4. Configuration XML

![Configuration XML](Screenshots/resultatXml.png)

`DaoImpl2` est injecté via `applicationContext.xml`. Résultat : **300.0**.

## 5. Test unitaire JUnit

![Test JUnit](Screenshots/test1.png)

Le test `MetierImplTest` vérifie que 10.0 × 2 = 20.0. **1 test passed**.

## 6. Profil `prod`

![Profil prod](Screenshots/Image4springdi.png)

Seul `DaoImpl` est actif : « Version de production ». Résultat : **200.0**.