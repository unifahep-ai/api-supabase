# Documentação da API REST - Supabase
## Criada por Any Karolyne - Futurisy

**URL Base:** `https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/`

## Autenticação e Headers Padrão
Todas as requisições exigem o seguinte cabeçalho:
* `apikey`: Sua chave pública anônima (anon key), encontrada nas configurações de API do seu painel Supabase.

---

## 1. Cursos (`courses`)

### Listar Cursos (GET)
```bash
curl -X GET '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/courses?select=](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/courses?select=)*' \
-H "apikey: SEU_SUPABASE_ANON_KEY"
```

### Criar Curso (POST)
```bash
curl -X POST '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/courses](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/courses)' \
-H "apikey: SEU_SUPABASE_ANON_KEY" \
-H "Content-Type: application/json" \
-H "Prefer: return=minimal" \
-d '{
  "name": "Engenharia de Software",
  "level": "Graduação"
}'
```

### Deletar Curso (DELETE)
```bash
curl -X DELETE '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/courses?id=eq.COLOQUE_O_UUID_AQUI](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/courses?id=eq.COLOQUE_O_UUID_AQUI)' \
-H "apikey: SEU_SUPABASE_ANON_KEY"
```

---

## 2. Perfis (`profiles`)

### Listar Perfis (GET)
```bash
curl -X GET '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/profiles?select=](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/profiles?select=)*' \
-H "apikey: SEU_SUPABASE_ANON_KEY"
```

### Criar Perfil (POST)
```bash
curl -X POST '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/profiles](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/profiles)' \
-H "apikey: SEU_SUPABASE_ANON_KEY" \
-H "Content-Type: application/json" \
-H "Prefer: return=minimal" \
-d '{
  "full_name": "João da Silva",
  "email": "joao@email.com",
  "password": "senha_criptografada_ou_hash",
  "role": "aluno",
  "status": "ativo",
  "cpf": "123.456.789-00",
  "course_id": "UUID_DO_CURSO_AQUI"
}'
```

### Deletar Perfil (DELETE)
```bash
curl -X DELETE '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/profiles?id=eq.COLOQUE_O_UUID_AQUI](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/profiles?id=eq.COLOQUE_O_UUID_AQUI)' \
-H "apikey: SEU_SUPABASE_ANON_KEY"
```

---

## 3. Requisitos de Documentos (`document_requirements`)

### Listar Requisitos (GET)
```bash
curl -X GET '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/document_requirements?select=](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/document_requirements?select=)*' \
-H "apikey: SEU_SUPABASE_ANON_KEY"
```

### Criar Requisito (POST)
```bash
curl -X POST '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/document_requirements](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/document_requirements)' \
-H "apikey: SEU_SUPABASE_ANON_KEY" \
-H "Content-Type: application/json" \
-H "Prefer: return=minimal" \
-d '{
  "name": "RG ou CNH",
  "is_required": true,
  "accepted_formats": ["pdf", "jpg", "png"],
  "expiry_days": 3650
}'
```


## 4. Documentos (`documents`)

### Listar Documentos (GET)
```bash
curl -X GET '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/documents?select=](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/documents?select=)*' \
-H "apikey: SEU_SUPABASE_ANON_KEY"
```

### Criar Documento (POST)
```bash
curl -X POST '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/documents](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/documents)' \
-H "apikey: SEU_SUPABASE_ANON_KEY" \
-H "Content-Type: application/json" \
-H "Prefer: return=minimal" \
-d '{
  "owner_id": "UUID_DO_PERFIL",
  "requirement_id": "UUID_DO_REQUISITO",
  "name": "rg_frente.pdf",
  "type": "application/pdf",
  "file_url": "https://url-do-bucket-storage",
  "ai_metadata": {"ocr_extracted": true, "confidence": 0.95},
  "observacao": "Documento legível"
}'
```

### Deletar Documento (DELETE)
```bash
curl -X DELETE '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/documents?id=eq.COLOQUE_O_UUID_AQUI](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/documents?id=eq.COLOQUE_O_UUID_AQUI)' \
-H "apikey: SEU_SUPABASE_ANON_KEY"
```

---

## 5. Logs de Auditoria (`audit_logs`)

### Listar Logs (GET)
```bash
curl -X GET '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/audit_logs?select=](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/audit_logs?select=)*' \
-H "apikey: SEU_SUPABASE_ANON_KEY"
```

### Criar Log de Auditoria (POST)
```bash
curl -X POST '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/audit_logs](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/audit_logs)' \
-H "apikey: SEU_SUPABASE_ANON_KEY" \
-H "Content-Type: application/json" \
-H "Prefer: return=minimal" \
-d '{
  "actor_id": "UUID_DO_ATENDENTE_OU_SISTEMA",
  "action": "DOCUMENT_APPROVED",
  "details": "O documento de identidade foi aprovado manualmente.",
  "aluno_id": "UUID_DO_ALUNO"
}'
```

### Deletar Log (DELETE)
```bash
curl -X DELETE '[https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/audit_logs?id=eq.COLOQUE_O_UUID_AQUI](https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/audit_logs?id=eq.COLOQUE_O_UUID_AQUI)' \
-H "apikey: SEU_SUPABASE_ANON_KEY"
```
