# Docs Validator

[![Stars](https://img.shields.io/github/stars/jeff2k3/doc-validator?style=social)](https://github.com/jeff2k3/doc-validator)
[![PHP Version](https://img.shields.io/badge/PHP-8.2%2B-777BB4.svg)](https://www.php.net/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

**Biblioteca PHP moderna e performática para validação de documentos brasileiros.**
 
## Documentos Suportados

| Documento              | Método                  | Tamanho | Dígitos Verificadores | Suporte Alfanumérico |
|------------------------|-------------------------|---------|-----------------------|----------------------|
| CPF                    | `Doc::CPF()`           | 11      | 2                     | Não                  |
| CNPJ                   | `Doc::CNPJ()`          | 14      | 2                     | **Sim** (novo formato) |
| CNH                    | `Doc::CNH()`           | 11      | 2                     | Não                  |
| NIS / PIS / PASEP      | `Doc::NIS()`           | 11      | 1                     | Não                  |
| Título de Eleitor      | `Doc::TITULO()`        | 12      | 2                     | Não                  |

## Instalação

```bash
composer require jeff2k3/doc-validator
```
##  Uso básico
### CPF
```php
$cpf = \Docs\Doc::CPF('123.456.789-09');

if ($cpf->checksum()) {
     echo 'CPF válido!';
}

echo $cpf->dv(); // Imprime: 09
```

# Métodos disponíveis

| Método | Descrição |
|---------|-----------|
| `checksum(): bool` | Valida os dígitos verificadores |
| `assertChecksum(string $expected): bool` | Compara resultado com valor esperado |
| `dv(): string` | Retorna os dígitos verificadores |

---

# Segurança

A biblioteca foi desenvolvida seguindo boas práticas para tratamento de informações sensíveis.

- Objetos imutáveis
- Mascaramento automático de documentos
- Compatível com LGPD
- Sem armazenamento de dados

---

# Testes

```bash
composer test
```
