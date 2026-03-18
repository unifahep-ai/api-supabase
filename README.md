# Documentação da API REST - Supabase

## Autenticação e Headers Padrão
Todas as requisições exigem o seguinte cabeçalho:
* `Authorization`

---

## 1. user_and_doc (`criado especificamente para analise via API`)
Essa documentação foi criada especificamente para criação e listagem de documentos verificados via API.

**como funciona:** 
- Primeiro é feito a inserção dos dados
- Após isso ele passa pela analise (que pode levar de 2 a 5 minutos)
- Depois é possivel fazer um get e pegar as informações (risco, ai_metadata, etc...)



### Criar user_and_doc (POST)
```bash
curl -L -X POST 'https://xynvcqxugvkmpxrmpsfv.supabase.co/functions/v1/upload-doc' \
  -H 'Authorization: Bearer ' \
  -F 'user_fullname=José da Silva' \
  -F 'user_cpf=01234567890' \
  -F 'user_rg=0123456789' \
  -F 'doc_type=RG_Frente' \
  -F 'user_address=avenida beira mar' \
  -F 'document=@/caminho/para/sua/imagem.jpg'
```

### Listar todos (GET)
```bash
curl -L -X GET 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/user_and_doc?select=*' \
  -H 'Authorization: Bearer '
```
### Filtrar por cpf (GET)
```bash
curl -L -X GET 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/user_and_doc?user_cpf=eq.01234567890&select=*' \
  -H 'Authorization: Bearer '
```
