# Documentação da API REST - Supabase

**URL Base:** `https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/`

## Autenticação e Headers Padrão
Todas as requisições exigem o seguinte cabeçalho:
* `apikey`: Sua chave pública anônima (anon key).

---

## 1. Cursos (`courses`)

### Listar Cursos (GET)
```bash
curl --location --request GET 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/courses?select=*' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```

### Criar Curso (POST)
```bash
curl --location 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/courses' \
--header 'apikey: SEU_SUPABASE_ANON_KEY' \
--header 'Content-Type: application/json' \
--header 'Prefer: return=minimal' \
--data '{
  "name": "Engenharia de Software",
  "level": "Graduação"
}'
```

### Deletar Curso (DELETE)
```bash
curl --location --request DELETE 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/courses?id=eq.COLOQUE_O_UUID_AQUI' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```

---

## 2. Perfis (`profiles`)

### Listar Perfis (GET)
```bash
curl --location --request GET 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/profiles?select=*' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```

### Criar Perfil (POST)
```bash
curl --location 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/profiles' \
--header 'apikey: SEU_SUPABASE_ANON_KEY' \
--header 'Content-Type: application/json' \
--header 'Prefer: return=minimal' \
--data '{
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
curl --location --request DELETE 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/profiles?id=eq.COLOQUE_O_UUID_AQUI' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```

---

## 3. Requisitos de Documentos (`document_requirements`)

### Listar Requisitos (GET)
```bash
curl --location --request GET 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/document_requirements?select=*' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```

### Criar Requisito (POST)
```bash
curl --location 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/document_requirements' \
--header 'apikey: SEU_SUPABASE_ANON_KEY' \
--header 'Content-Type: application/json' \
--header 'Prefer: return=minimal' \
--data '{
  "name": "RG ou CNH",
  "is_required": true,
  "accepted_formats": ["pdf", "jpg", "png"],
  "expiry_days": 3650
}'
```

### Deletar Requisito (DELETE)
```bash
curl --location --request DELETE 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/document_requirements?id=eq.COLOQUE_O_UUID_AQUI' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```

---

## 4. Documentos (`documents`)

### Listar Documentos (GET)
```bash
curl --location --request GET 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/documents?select=*' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```

### Criar Documento (POST)
```bash
curl --location 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/documents' \
--header 'apikey: SEU_SUPABASE_ANON_KEY' \
--header 'Content-Type: application/json' \
--header 'Prefer: return=minimal' \
--data '{
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
curl --location --request DELETE 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/documents?id=eq.COLOQUE_O_UUID_AQUI' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```

---

## 5. Logs de Auditoria (`audit_logs`)

### Listar Logs (GET)
```bash
curl --location --request GET 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/audit_logs?select=*' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```

### Criar Log de Auditoria (POST)
```bash
curl --location 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/audit_logs' \
--header 'apikey: SEU_SUPABASE_ANON_KEY' \
--header 'Content-Type: application/json' \
--header 'Prefer: return=minimal' \
--data '{
  "actor_id": "UUID_DO_ATENDENTE_OU_SISTEMA",
  "action": "DOCUMENT_APPROVED",
  "details": "O documento de identidade foi aprovado manualmente.",
  "aluno_id": "UUID_DO_ALUNO"
}'
```

### Deletar Log (DELETE)
```bash
curl --location --request DELETE 'https://xynvcqxugvkmpxrmpsfv.supabase.co/rest/v1/audit_logs?id=eq.COLOQUE_O_UUID_AQUI' \
--header 'apikey: SEU_SUPABASE_ANON_KEY'
```
