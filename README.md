# PEC - Elaine — GitHub e Vercel

Exportação de 26/10/2026. Site estático: HTML, CSS, JavaScript, JSON e imagens.
Inclui Américo Sugai, Paulo Tapajós, Heráclides, Arlindo Aquino e Enedina, com os dados atualmente incorporados ao portal. Firmino ainda não foi incluído.
Inclui a atualização do 2º bimestre do Médio/Técnico da Enedina. O último arquivo de resultados por questão enviado ainda não foi incorporado.

## Dados dos alunos e acesso
Os nomes e resultados foram mantidos. Crie um repositório PRIVADO no GitHub.
O acesso privado do ChatGPT NÃO acompanha esta exportação. Não existe login próprio neste código. Um repositório privado não torna a publicação do Vercel privada.
Proteja a publicação em Settings > Deployment Protection com Vercel Authentication, abrangendo TODAS as publicações, inclusive os domínios de produção. Standard Protection pode deixar o domínio de produção aberto. Confira o escopo informado na sua conta.
Faça isso antes de enviar os arquivos para implantação, preferencialmente no projeto vazio já existente. Não use apenas uma senha desenhada em JavaScript: os arquivos JSON continuariam acessíveis.
Autorize as pessoas das escolas pelo mecanismo de proteção escolhido. Vercel Authentication usa conta Vercel; não exige ChatGPT. Opções e custos de convite/senha podem depender do plano. Se precisar de login individual por escola, esse controle ainda precisa ser desenvolvido.
X-Robots-Tag reduz indexação; NÃO controla acesso.

## 1. Preparar no computador
1. Baixe o ZIP e clique com o botão direito > Extrair tudo.
2. Abra a pasta pec-elaine. Nela existem dist, vercel.json, README.md e .gitignore.
3. Não abra index.html com duplo clique para testar: a leitura de JSON requer servidor HTTP. Teste pela publicação, ou use python -m http.server 8000 --directory dist se tiver Python.

## 2. Colocar no GitHub
1. Acesse https://github.com e entre na sua conta.
2. Clique + > New repository.
3. Nome sugerido: pec-elaine. Selecione Private e marque Add a README file. Clique Create repository.
4. Abra Add file > Upload files.
5. Dentro da pasta extraída pec-elaine, arraste a pasta dist e os arquivos vercel.json e README.md. Não envie somente o ZIP nem arraste a pasta externa pec-elaine.
6. Clique Commit changes. Se o navegador limitar a 100 arquivos, faça mais de um envio mantendo os caminhos de cada pasta. Alternativa: GitHub Desktop para enviar a pasta completa.
7. Confirme que a raiz contém vercel.json e dist; dentro de dist deve existir index.html.
8. Mantenha o repositório privado. Não habilite GitHub Pages.

## 3. Preparar a proteção no Vercel
1. Acesse https://vercel.com com a sua conta.
2. Se for reutilizar o projeto vazio pec-elaine-americo-sugai, abra-o. O nome visível do projeto pode ser alterado em Settings > General para pec-elaine, se disponível.
3. Abra Settings > Deployment Protection e habilite a proteção também para produção (All Deployments, ou opção equivalente que explicitamente inclua os domínios de produção).
4. Salve. Confirme que o domínio principal não está entre as exceções de proteção.
5. Se a sua conta não disponibilizar a proteção desejada, mantenha os dados nominais fora de uma implantação pública até escolher uma alternativa de acesso.

## 4. Conectar GitHub e publicar
Projeto existente: Settings > Git > Connect Git Repository, autorize o GitHub e selecione seu repositório privado pec-elaine. Autorize somente esse repositório quando possível.
Projeto novo: Add New > Project > Import Git Repository. Selecione pec-elaine e configure a proteção da produção antes de implantar os dados nominais. Se o fluxo não permitir proteção antecipada, use primeiro um repositório vazio com uma página sem dados e configure a proteção antes de enviar dist.

Configurações:
- Framework Preset: Other.
- Root Directory: raiz do repositório, sem escolher dist.
- Build Command: vazio/desabilitado.
- Install Command: vazio/desabilitado.
- Output Directory: dist.
- Environment Variables: nenhuma.
- Production Branch: main.
O arquivo vercel.json já define os comandos vazios e a saída dist. Não é necessário npm install nem banco de dados.
Clique Deploy (ou Deployments > Create Deployment para a branch main, se a conexão não iniciar uma publicação). Aguarde Ready. Abra Visit para obter o endereço real. Não há um novo endereço publicado por esta entrega.

## 5. Conferir e disponibilizar às escolas
1. Em uma janela anônima, abra a URL principal: deve solicitar a autenticação/proteção escolhida.
2. Teste também /data.json e /enedina-pp.json: devem ficar igualmente protegidos. Se abrirem sem autorização, a publicação está pública; corrija o escopo antes de compartilhar.
3. Entre com acesso autorizado e confira as cinco escolas, filtros, nomes, grupos de nivelamento e Foco do Trabalho.
4. Na Enedina, confira Ensino Médio/Técnico > Prova Paulista > 2º bimestre > Física/Digital.
5. Autorize os destinatários pelo controle do Vercel e envie o endereço de produção a eles. Quem tem acesso ao portal exportado consegue consultar os dados de todas as escolas; não existe separação de permissão por escola.
6. Teste em um computador da escola. O site não depende do ChatGPT para funcionar. Se o filtro da rede também bloquear vercel.app, solicite à equipe de TI liberação do domínio ou use um domínio institucional autorizado.
7. Controles e observações que já eram locais ao navegador continuam locais; não há sincronização compartilhada de anotações nesta exportação.

## 6. Atualizar depois
Substitua os arquivos alterados nos MESMOS caminhos do GitHub e confirme em main. Com a integração Git ativa, o Vercel cria a atualização automaticamente. Mudanças feitas no portal do ChatGPT não são sincronizadas com este novo repositório: será preciso exportar/enviar as alterações.

## Problemas comuns
- 404: raiz incorreta, dist ausente ou ZIP enviado sem extrair.
- Painel vazio: JSON/JavaScript faltando, nomes dos arquivos alterados, ou teste feito por file://.
- Projeção antiga: confira o último deployment Ready e a branch main.
- Acesso bloqueado na escola: confira o domínio com a TI; hospedar fora do ChatGPT não garante liberação pela rede escolar.
- Não edite os arquivos JSON manualmente sem preservar a estrutura.

## Documentação oficial
https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
https://vercel.com/docs/builds/configure-a-build
https://vercel.com/docs/git
https://vercel.com/docs/deployment-protection/methods-to-protect-deployments/vercel-authentication
