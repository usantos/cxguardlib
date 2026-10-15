<!-- cxguard-public-maven:0.17.1 -->
# CXGuard — Maven público

Repositório de distribuição dos binários comerciais do CXGuard 0.17.1.
Download público e sem autenticação: `https://usantos.github.io/cxguardlib/`.
O software permanece proprietário; baixar os arquivos não concede licença de uso.
A licença anual por aplicativo é emitida separadamente pelo fornecedor no painel CXGuard.
Consulte `LICENSE-CXGuard.txt`. O repositório de código-fonte permanece privado.

Adicione este Maven em `pluginManagement.repositories` e em
`dependencyResolutionManagement.repositories` no `settings.gradle.kts`:

```kotlin
maven { url = uri("https://usantos.github.io/cxguardlib/") }
```

Plugin: `id("br.com.cxguard") version "0.17.1"`.
Runtime: `implementation("br.com.cxguard:cxguard-runtime:0.17.1")`.
Não configure usuário, senha, PAT ou token GitHub para baixar essas dependências.
Forneça a licença CXGuard separadamente no build:
`-PcxguardLicenseFile=/caminho/privado/aplicativo.license`.

São distribuídos somente AAR/JAR/POM e os checksums SHA-256/SHA-1.
Não são distribuídos fontes, emissor, chaves privadas nem licenças de clientes.
