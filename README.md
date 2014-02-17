Guia Rápido
----------------------

Consiste de um guia rápido para que você possa usá=loo como base para seu próprio instalador. 

* Config File: O PagodaBox precisa de um arquivoo de configuração diferente do que a versão local do site, criamos um novo diretório na raiz do projeto chamado "pagoda" e foi colocado uma versão do arquivo de configuração do Wordpress. Então criamos um hook para ser construido durante o deploy, esse hook é composto pelo arquivo Boxfile que executa algumas tarefas logo após a atualização dos arquivos no servidor do PagodaBox. Além disso, no lugar das credenciais de banco de dados estáticos, foram utilizadas as variáveis ​​de ambiente de auto-criado.

<pre>
    <code>
        after_build:
        - "mv pagoda/wp-config.php wp-config.php"
        - "mv pagoda/.htaccess .htaccess"
    </code>
</pre>  


* Database Component:  Uma base de dados vazia foi criado pela adição de um componente para o db do Boxfile.

<pre>
    <code>
        db1:
            name: wp-db
    </code>
</pre>