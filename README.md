# Домашнее задание к занятию «Сетевые технологии, ключевые устройства»

## Задача «Знакомство с Wireshark»

<details>
<summary>Предварительные действия.</summary>
Используйте виртуальную машину с Kali Linux и указанные в предыдущем разделе файлы. Если машина с Kali Linux у вас не запускается, вам придётся самостоятельно установить [Wireshark с официального сайта](https://www.wireshark.org/download.html) и использовать соответствующие исполняемые файлы из каталога [assets](assets).

#### Выполнение

1\. Откройте виртуальную машину, в поисковой строке введите `wireshark`:

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/01.png)

2\. Вас попросят ввести пароль вашего пользователя для подтверждения (`kali`, если вы скачивали OVA с официального сайта):

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/02.png)

3\. В запустившемся окне вам необходимо выбрать интерфейс `Loopback: lo`

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/03.png)

4\. Сохраните файлы в каком-либо каталоге (например, в `Downloads`):
1. [server-x64.bin](https://raw.github.com/netology-code/ibnet-homeworks/tree/master/02_intro/assets/server-x64.bin)
1. [text-x64.bin](https://raw.github.com/netology-code/ibnet-homeworks/tree/master/02_intro/assets/text-x64.bin)
1. [task-x64.bin](https://raw.github.com/netology-code/ibnet-homeworks/tree/master/02_intro/assets/task-x64.bin)

4\. Откройте терминал в данном каталоге (см. [руководство по терминалу](../terminal), открывается аналогично Ubuntu):

5\. Выполните в первой вкладке следующую команду (выставление прав на запуск приложений): `chmod +x *.bin`

6\. Запустите в первой вкладке сервер командой: `./server-x64.bin`

7\. Запустите во второй вкладке тестовый клиент для отправки сообщения: `./text-x64.bin "Hello, World"` (сервер должен продолжать работать)

8\. В окне Wireshark вы должны увидеть следующее:

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/08.png)

9\. Щёлкните правой кнопкой мыши на первой строке и выберите опции как на скриншоте:

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/09.png)

10\. Вы увидите взаимодействие между клиентом и сервером в текстовом виде в кодировке ASCII:

![](https://raw.githubusercontent.com/netology-code/ibnet-homeworks/master/02_intro/pic/10.png)

11\. Запустите целевой клиент во второй вкладке: `./task-x64.bin`

Попробуйте проанализировать сетевое взаимодействие целевого клиента с сервером. В качестве сообщения клиент должен передать хэш SHA-256. Воспользуйтесь в этот раз не hashcat, а предвычисленными таблицами для хэшей, например [crackstation.net](https://crackstation.net) для подбора захэшированного сообщения. Если  не получится через [crackstation.net](https://crackstation.net), то поробуйте через [hashes.com](https://hashes.com/)

</details>