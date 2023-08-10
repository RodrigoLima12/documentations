## Passo a apasso para gerar o arquivo .APK do projeto Flutter 🚀

>Obs: A cada atualização alterar a tag.

### 1. Fazer o commit das alterações
Realizar o commit de acordo com o que foi modificado.

### 2. Verificar tags
Verificar as tags para idenficar a última criada e incrementar para a criação de uma nova. Deve-se utilizar:
```bash
  git tag
```

### 3. Criar a tag: git tag {nome da tag};
A partir da ultima tag feita, criar uma nova (icrementando o ultimo numero). Deve-se utilizar
```bash
  git tag {numeracao_da_tag_incrementada}
```

### 4. Subir a tag
Deve-se utilizar:
```bash
  git push origin {tag_criada}
```
>Obs: antes de ir para o próximo passo, caso tenham alterações em outros repos (core, desing system, etc), é necessário que os PRs ja tenha sido mergeados.

### 5. Ir para o repositório do ana_base
No pubspec, alterar a versão do app, alterar a versão ref do ana_admissao para a tag criada.

### 6. Deletar o arquivo pubspec.lock do ana base
Após deletar, é necessário atualizar os pacotes. Deve-se utilizar:
```
  flutter pub get
```

### 7. Subir o commit e analisar se não tem pacotes em override
Ainda no ana base, deve-se subir o commit com as alterações no pubspec e fazer o push diretamente na branch em development (NÃO SUBIR OVERRIDE);

### 8. Ir no github do repo da ana_base para verificar o build
Na aba "actions" do repositório do ana_base estarão sendo feitos os builds do app para android, web e ios. Deve-se escolher o build do android, abrir e procurar por "Upload to S3".
Encontrar a linha que contenha o link e copiar
>Obs: deve-se ajustar o link (adicionar o "https://" no lugar do "s3", adicionar o csdn e trocar os + por "%2B"). Deve ficar da seguinte forma: https://nasajon-cdn.s3.sa-east-1.amazonaws.com/github%2Bfastlane/dev/android/v0.0.0-000/app-dev-release.apk

### 9. Baixar o APK.
Com o link ajustado e copiado, acessa-lo e baixar o APK.
