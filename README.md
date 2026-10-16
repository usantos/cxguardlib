<!-- cxguard-public-maven:0.17.3 -->
# CXGuard — Maven público

Repositório de distribuição dos binários comerciais do CXGuard 0.17.3.
Download público e sem autenticação: `https://usantos.github.io/cxguardlib/`.
O software permanece proprietário; baixar os arquivos não concede licença de uso.
A licença anual por aplicativo é emitida separadamente pelo fornecedor no painel CXGuard.
Consulte `LICENSE-CXGuard.txt`. O repositório de código-fonte permanece privado.

Adicione este Maven em `pluginManagement.repositories` e em
`dependencyResolutionManagement.repositories` no `settings.gradle.kts`:

```kotlin
maven { url = uri("https://usantos.github.io/cxguardlib/") }
```

Plugin: `id("br.com.cxguard") version "0.17.3"`.
Runtime: `implementation("br.com.cxguard:cxguard-runtime:0.17.3")`.
Não configure usuário, senha, PAT ou token GitHub para baixar essas dependências.
Forneça a licença CXGuard separadamente no build:
`configure<br.com.cxguard.gradle.CXGuardExtension> { licenseTokenFile.set(file("/caminho/privado/aplicativo.license")) }`.
Essa atribuição explícita é obrigatória; `-PcxguardLicenseFile` sozinha não configura a licença.
Sem arquivo explicitamente configurado, existente e legível, a sincronização do Android Studio e o build falham durante a configuração do projeto.

São distribuídos somente AAR/JAR/POM e os checksums SHA-256/SHA-1.
Não são distribuídos fontes, emissor, chaves privadas nem licenças de clientes.
