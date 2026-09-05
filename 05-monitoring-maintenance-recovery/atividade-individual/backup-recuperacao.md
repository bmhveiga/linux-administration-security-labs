
Backup e Recuperação
Objetivo

Criar um backup simples do serviço web e testar a recuperação numa pasta de teste.

Itens críticos identificados

Foram considerados críticos:

/var/www/html: conteúdo publicado do site;
/etc/nginx/sites-available/default: configuração principal do site Nginx.
Backup criado

Foi criado um ficheiro .tar.gz com o conteúdo web e a configuração Nginx.

Ficheiro de backup:

evidencias/backup-web-nginx-topico-05.tar.gz

Recuperação testada

O backup foi restaurado numa pasta de teste:

/tmp/topico-05-restore-test

Isto permitiu confirmar que os ficheiros foram recuperados sem alterar diretamente o serviço em produção.

Validação após recuperação

A validação confirmou:

o ficheiro de backup foi criado;
o conteúdo do backup podia ser listado;
os ficheiros foram restaurados numa pasta de teste;
o serviço original continuou acessível após o backup.
Evidência

A evidência está em:

evidencias/topico-05-backup-recuperacao.txt

Conclusão

O backup e a recuperação simples foram realizados com sucesso. A restauração foi testada em ambiente seguro, sem substituir diretamente os ficheiros originais do serviço.
