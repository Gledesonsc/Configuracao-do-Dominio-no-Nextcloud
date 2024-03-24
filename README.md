# Configuração do Domínio no Nextcloud

Neste guia, você aprenderá como configurar o domínio no Nextcloud em um ambiente Ubuntu usando o terminal. Certifique-se de ter acesso de superusuário ou use `sudo` conforme necessário.

## Passo 1: Localize o Arquivo de Configuração

```bash
ubuntu@adapanel:~$ sudo su -
root@adapanel:~# find / -name config.php
/etc/easypanel/projects/drive/nextcloud/volumes/data/config/config.php
/var/lib/docker/volumes/drive_nextcloud_data/_data/config/config.php
```

Identifique o arquivo de configuração do Nextcloud. Vamos supor que o caminho seja `/var/lib/docker/volumes/drive_nextcloud_data/_data/config/config.php`.

## Passo 2: Edite o Arquivo de Configuração

```bash
root@adapanel:~# nano /var/lib/docker/volumes/drive_nextcloud_data/_data/config/config.php
```

Abra o arquivo de configuração usando o editor Nano. Este arquivo contém as configurações do Nextcloud.

## Passo 3: Atualize as Configurações de Domínio

Procure a seção de configuração do domínio no arquivo. Geralmente, é algo como:

```php
'overwrite.cli.url' => 'http://localhost/nextcloud',
```

Altere `http://localhost/nextcloud` para o seu domínio desejado. Por exemplo:

```php
'overwrite.cli.url' => 'http://seu-dominio.com/nextcloud',
```

## Passo 4: Salve e Feche o Arquivo

Pressione `Ctrl + O` para salvar as alterações e `Ctrl + X` para fechar o editor Nano.

## Passo 5: Reinicie o Serviço Nextcloud

Depois de fazer as alterações, é necessário reiniciar o serviço Nextcloud para que as alterações entrem em vigor.

```bash
root@adapanel:~# docker-compose restart nextcloud
```

Isso reiniciará o contêiner do Nextcloud para aplicar as novas configurações.

## Conclusão

Parabéns! Você configurou com sucesso o domínio no Nextcloud. Agora você pode acessar o Nextcloud usando o novo domínio configurado.

🎉🚀✨
