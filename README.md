# SalesWebMvc

Sistema web de vendas em **ASP.NET Core MVC** com Entity Framework Core e MySQL: cadastro de departamentos e vendedores e consulta de registros de venda por período.

> Projeto de estudo (fevereiro/2022), feito para praticar o padrão MVC, camada de serviços e o EF Core de ponta a ponta.

## Funcionalidades

- CRUD de **departamentos** e **vendedores** (vendedor com departamento escolhido numa lista)
- Detalhes do vendedor com carregamento antecipado (eager loading) do departamento
- **Busca simples** de vendas entre duas datas
- **Busca agrupada** de vendas por departamento
- Validação de formulários no servidor e no navegador
- Formatação de números e datas por cultura e página de erro personalizada
- Exceções de serviço próprias (`NotFoundException`, `IntegrityException`, `DbConcurrencyException`), por exemplo ao tentar remover um vendedor que tem vendas
- Banco populado automaticamente por um `SeedingService` em desenvolvimento

## Modelo

```
Department 1 ── N Seller 1 ── N SalesRecord (data, valor, status)
```

## Tecnologias

- ASP.NET Core 2.1 MVC com Razor
- Entity Framework Core 2.1 com Pomelo (MySQL)
- Bootstrap e jQuery Validation

## Como executar

Pré-requisitos: SDK do .NET Core 2.1 e um MySQL rodando.

> O .NET Core 2.1 já saiu de suporte. Para rodar num ambiente atual, instale o SDK 2.1 em paralelo ou atualize o `TargetFramework` e os pacotes.

1. Ajuste a connection string `SalesWebMvcContext` em `SalesWebMvc/appsettings.json`.
2. Crie o banco:
   ```bash
   dotnet ef database update --project SalesWebMvc
   ```
3. Rode a aplicação:
   ```bash
   dotnet run --project SalesWebMvc
   ```

---

Feito por **Mikael Francisco** · [Portfólio](https://mikaelfrancisco.vercel.app) · [LinkedIn](https://www.linkedin.com/in/mikael-francisco-a4300b180)
