Uma fake API para uma aplicação de todos

Base URL: https://todo-fake-api.onrender.com

## ROTAS

## todos

### Ler Todos /todos GET (Requer autorização)

```json
{
   "Authorization": "Bearer token"
}
```

Padrão de resposta:

```json
[
   {
      "id": 1,
      "title": "Lavar louça",
      "content": "Não esquece"
   }
]
```

#### Parâmetros
userId (para buscar notas somentes de um determinado usuário)

### Criar Todo /todos POST (Requer Autorização)

```json
{
   "Authorization": "Bearer token"
}
```

Padrão de corpo

```json
{
   "title": "Lavar louça",
   "content": "Não esquece",
   "userId": 1,
}
```

Padrão de resposta

```json
{
   "id": 1,
   "title": "Lavar louça",
   "content": "Não esquece",
   "userId": 1,
}
```

### Excluir Todo /todos/:todoId DELETE (Requer Autorização)

```json
{
   "Authorization": "Bearer token"
}
```

### Editar Todo /todos/:todoId PATCH (Requer Autorização)

```json
{
   "Authorization": "Bearer token"
}
```

Padrão de corpo (não é necessário o corpo completo, somente os valores atualizados)

```json
{
   "title": "Lavar louça",
   "content": "Não esquece"
}
```

Padrão de resposta

```json
{
   "id": 1,
   "title": "Lavar louça",
   "content": "Não esquece",
   "userId": 1,
}
```

Não tem um corpo de resposta, nem precisa de um corpo

## Usuário

## Registrar Usuário /users POST

Padrão de corpo

```json
{
   "name": "José da Silva",
   "email": "josedasilva@email.com",
   "password": "123456"
}
```

## Login de Usuário /login POST

Padrão de corpo

```json
{
   "email": "josedasilva@email.com",
   "password": "123456"
}
```

Padrão de Resposta

```json
{
   "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImpvaG5kb2VAZW1haWwuY29tIiwiaWF0IjoxNjgxMjI2MzU1LCJleHAiOjE2ODEyMjk5NTUsInN1YiI6IjIifQ.HoHzAjg6luV9k6v8zHyewSTHsUnAKDBIbFiIS0r_joM",
   "user": {
      "name": "José da Silva",
      "email": "josedasilva@email.com",
      "id": 1
   }
}
```

### Usuário (Autologin) /users/:userId GET (Requer Autorização)

Headers

```json
{
   "Authorization": "Bearer token"
}
```

Padrão de resposta

```json
{
   "name": "José da Silva",
   "email": "josedasilva@email.com",
   "id": 1
}
```
