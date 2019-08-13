p { margin-bottom: 0.25cm; line-height: 115%; }a:link { }

_1) Установить
последний ansible из репозитория;_

_2) __Скачать
директорию ansible с [https://github.com/vorobyovms/ansible](https://github.com/vorobyovms/ansible)
, распаковать и скопировать в   /etc/ansible
с заменой._

_3__) Правим
файл /etc/ansible/hosts_

_**По умолчанию
там:**_

_**[local]**_

_**vm
ansible_ssh_host=127.0.0.1 ansible_ssh_port=2222**_

_**Хост(ы)
входят в группу local**_

_4) Далее правим __если надо
__**/etc/ansible/group_vars/local/local.yml**_

_**Тут **__**по умолчанию**_

_**---**_

_**ansible_ssh_user:
sysadmin                                                 //логин
к сервервам**_

_**ansible_ssh_pass:
kfvth20cdn                                              //pass**_

_**apachesrc:
/etc/ansible/roles/apache2/files/apache2          //откуда
будет копироваться дирек               с конф
АПАЧА**_

_**apachedst:
/etc                                                                 
   //КУДА БУДЕТ КОПИРОВАТЬСЯ**_

_**package_for_install:
apache2,libapache2-mod-geoip,apache2-data,apache2-bin,apache2-utils
//ПАКЕТЫ ДЛЯ УСТАНОВКИ**_

_**index:
/etc/ansible/roles/apache2/files/apache2/conf.d/autoindex.conf**_

_**index_dst:
/etc/apache2/conf.d/autoindex.conf**_

_5) Запускаем
/usr/bin/ansible-playbook /etc/ansible/apache2.yml -vvvv_
