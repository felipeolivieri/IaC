# IaC
Lab de infraestrutura como codigio usando Vagrant e Ansible - lab feito com wordpress

Este repositorio é um repositorio de estudo de Vagrant e Ansible. 

A idéia é utilizar estas ferramentas para levantar um ambiente de wordpress baseado em ubuntu, mysql, apache e php.

No código do ansible, estou usando as melhores práticas de separar os servidores, group_vars, variaveis para configurar arquivos de configurações etc.

Mas todo o processo começou de forma simples e evoluindo conforme meus estudos. Isso pode ser osbservado variamente ao longo dos commits.

Sobre o ambiente:
Este ambiente é composto por 3 máquinas virtuais:
1. ansible
2. mysql
3. wordpress

Disponibilizei o ansible com uma versão de ubuntu para realizar os testes. achei melhor que instalar no meu macbook, até porque ajuda quem usa windows a testar, já que não tem ansible para windows.

Todas as VMs são disponibilizadas via Vagrantfile.
Leia o arquivo e altere para atender seu ambiente, configurações de IPs e achave de criptografia podem dar problemas no seu ambiente.

Requisitos:
Este ambiente foi feito em cima de VirtualBox, portanto é um requisito. Mas o código é reaproveitavel se desejar alterar para outro "provider", como VMware Fusion/workstation, hyper-V etc. Para isso altere o Vagrantfile.

<este documento ainda está sendo produzido>
