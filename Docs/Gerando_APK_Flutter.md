## Gerar o arquivo .APK do projeto Flutter

`Obs: A cada atualização alterar a tag;`

l. Fazer o commit das alterações;

l. Verificar tags (git tag) e criar uma nova a partir da ultima;

l. Criar a tag: git tag {nome da tag};

l. Subir a tag: git push origin {nome_da_tag};
Obs: antes de ir para o próximo passo, caso tenham alterações em
outros repos (core, desing system, etc), é necessário que os PRs
ja tenha sido mergeados;

l. Ir para o repositório do ana_base. No pubspec, alterar
a versão do app, alterar a versão ref do ana_admissao
para a tag criada;

l. Deletar o pubspec.lock do ana base e rodar: flutter pug get;

l. Ainda no ana base, subir o commit com as alterações no pubspec e
fazer o push diretamente na branch em development (NÃO SUBIR OVERRIDE);

l. Ir no github do repo da ana_base e em actions. Estarão sendo feitos
os builds do app para android, web e ios. Escolher o build do android,
abrir o build e procurar por "Upload to S3". Encontrar a linha do link
copiar, ajustar o link com "https://" e trocar os + por "%2B";

l. Com o link, é só baixar o APK.