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

```![VM2](https://github.com/nakhorenko/otus-pxe/assets/95616708/ad18ca92-87f7-442a-8985-61eca2abd06f)

~/Linux-2022-12/otus-pxe$ vagrant up pxeclient
```
И смотрим в графический интерфейс virtualbox
![VM](https://github.com/nakhorenko/otus-pxe/assets/95616708/b3c3acdd-7df3-4d24-a9ef-460272c59c9d)

![VM2](https://github.com/nakhorenko/otus-pxe/assets/95616708/4c03749b-529b-4204-81b2-a682ab819823)
