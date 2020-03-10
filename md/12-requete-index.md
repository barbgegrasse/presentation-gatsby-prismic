## Première requête GraphQL

Création de la requête dans GraphiQL
On copie/colle dans index.js
Le résultat de la requête est ensuite disponible en tant que props

#### index.js

```javascript
export const pageQuery = graphql`
    query MyQuery {
        ...
    }
`;
```
