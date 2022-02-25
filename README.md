# Laboratório de máquinas virtuais com Vagrant


![Vagrant Image!](./vagrant.png)

Versão do vagrant utilizada: **2.2.14**

Utilizo os seguintes Vagrantfiles para poder agilizar no processo de validação/configuração de ambientes. Nesse arquivo é iniciado múltiplas vm's.
<br>
<br>
<br>
<br>
Cada arquivo realiza o uso de determinado S.O. de preferência. Sendo o CentOS, Ubuntu ou Debian.
<br>
<br>
Realize o download da versão em uso: https://releases.hashicorp.com/vagrant/2.2.14/vagrant_2.2.14_x86_64.deb

Após o clone do repositório, para subir as máquinas virtuais é necessário ter o virtualbox instalado.
<br>
<br>
Obs: Lembre-se de alterar o ip para a faixa da rede a que você pertence e também para a interface de rede do dispositivo em que foi montado o lab.
<br>
<br>

- Inicie as máquinas aplicando o comando: <code>vagrant up</code> , dentro do diretório clonado.

- Para o desligamento de todas a máquinas execute o comando: <code> vagrant halt</code>

- Para remoção das máquinas virtuais: <code> vagrant destroy</code>

- Consulte mais comandos: <code>vagrant --help</code>