# otus-pxe
Цель домашнего задания
Отработать навыки установки и настройки DHCP, TFTP, PXE загрузчика и автоматической загрузки

1 Шаг: Установка pxeserver и настройка с помощью ansible
```
~/Linux-2022-12/otus-pxe$ vagrant up pxeserver
```
После успешной настройки, проверяем доступность httpd сервера и файлов, на нём
![centos8](https://github.com/nakhorenko/otus-pxe/assets/95616708/7fc577a1-ecb9-447b-bbef-38e9bc4f50c2)

Далее запускаем второй сервер

```

~/Linux-2022-12/otus-pxe$ vagrant up pxeclient
```
И смотрим в графический интерфейс virtualbox
![boot](https://github.com/nakhorenko/otus-pxe/assets/95616708/436b55dd-3fda-4db5-abf7-1efe4715d2e9)

![VM2](https://github.com/nakhorenko/otus-pxe/assets/95616708/4c03749b-529b-4204-81b2-a682ab819823)

Пришлось установить timezone, но затем яэто сделал в ks.cfg файле, чтобы запустилась автоматическая установка ОС
