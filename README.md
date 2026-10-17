<!-- cxguard-public-maven:0.19.0 -->
# CXGuard — Maven público

Repositório de distribuição dos binários comerciais do CXGuard 0.19.0.
Download público e sem autenticação: `https://usantos.github.io/cxguard-android-lib/`.
O software permanece proprietário; baixar os arquivos não concede licença de uso.
A licença anual por aplicativo é emitida separadamente pelo fornecedor no painel CXGuard.
Consulte `LICENSE-CXGuard.txt`. O repositório de código-fonte permanece privado.

Adicione este Maven em `pluginManagement.repositories` e em
`dependencyResolutionManagement.repositories` no `settings.gradle.kts`:

```kotlin
maven { url = uri("https://usantos.github.io/cxguard-android-lib/") }
```

Plugin: `id("br.com.cxguard") version "0.19.0"`.
Runtime: `implementation("br.com.cxguard:cxguard-runtime:0.19.0")`.
Não configure usuário, senha, PAT ou token GitHub para baixar essas dependências.
Forneça a licença CXGuard separadamente no build:
`configure<br.com.cxguard.gradle.CXGuardExtension> { licenseTokenFile.set(file("/caminho/privado/aplicativo.license")) }`.
Essa atribuição explícita é obrigatória; `-PcxguardLicenseFile` sozinha não configura a licença.
Sem arquivo explicitamente configurado, existente e legível, a sincronização do Android Studio e o build falham durante a configuração do projeto.

São distribuídos somente AAR/JAR/POM e os checksums SHA-256/SHA-1.
Não são distribuídos fontes, emissor, chaves privadas nem licenças de clientes.

## Renomeação do repositório em 17/10/2026

Este repositório foi renomeado de `usantos/cxguardlib` para `usantos/cxguard-android-lib`. A mudança organiza a distribuição Android separadamente das fontes privadas e do projeto principal. Nenhum binário, checksum, versão ou tag foi modificado nesta migração.

**Ação necessária no Maven:** atualize a URL em `pluginManagement.repositories` e em `dependencyResolutionManagement.repositories` para `https://usantos.github.io/cxguard-android-lib/`. O GitHub não garante redirecionamento de URLs de projeto GitHub Pages após renomear um repositório. O caminho antigo `/cxguardlib/` pode falhar; os links Git e de tags usam o redirecionamento do repositório. O nome antigo não será recriado, preservando esse redirecionamento. [Comportamento documentado pelo GitHub](https://docs.github.com/en/repositories/creating-and-managing-repositories/renaming-a-repository).

### Histórico API preservado

As pastas `api/0.1.0` e `api/0.2.0`, os artefatos Maven `br/com/cxguard/cxguard-api-server`, os manifestos, avisos e tags `api-v0.1.0`/`api-v0.2.0` já existiam no antigo repositório. Eles permanecem aqui como histórico de distribuição **API**, com seus bytes, checksums e tags originais. Não são versões Android nem uma nova publicação. Uma eventual distribuição API em repositório próprio será uma migração separada; nenhum repositório API separado existe nesta reorganização.

Fontes Android: repositório privado `usantos/cxguard-android`. Projeto principal, painel e backend API: privado `usantos/cxguard`. Distribuição iOS: [cxguard-ios-lib](https://github.com/usantos/cxguard-ios-lib), independente. A licença CXGuard assinada, a identidade e a validade continuam obrigatórias.
