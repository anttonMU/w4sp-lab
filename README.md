# ИСТОРИЯ

1. Первая версия настоящего проекта находится [здесь](https://github.com/w4sp-book/w4sp-lab/wiki/Lab-Installation).
2. Вторая версия настоящего проекта находится [здесь](https://medium.com/@vaibjav2raj/setting-up-the-w4sp-lab-in-2020-d4df6a3d2a5e).
Во второй версии настойщий проект был переписан с python2 на python3.
3. Третье версией является проект, в котором вы сейчас находитесь.

# ВВЕДЕНИЕ

Это лабораторная среда для книги Wireshark for Security Professionals: Using Wireshark and the Metasploit Framework. 
Для удобства изучения лаборатории можно обратиться ко 2 главе этой книги. Лаборатория построена на Docker и Kali Linux 
и предоставляет реалистичную сеть с многочисленными сервисами, полезными для изучения основ безопасности с помощью Wireshark.

# Установка

## !!!ВНИМАНИЕ!!!
1. Тестирование работоспособности проводилось только на Kali Linux 2020.2. Предположительно установка должна работать на 
Kali Linux 2020.Х и Ubuntu 20.Х. Возможно будет работать и на более поздних версиях.
2. В связи с нестабильной геополитической обстановкой для российских пользователей на всем потяжении установки
необходимо использовать VPN. VPN нужно включать либо на виртуальной машине, либо на хосте, если виртуальная машина
подключена через NAT.
 
## Начало установки

3. После того, как вы настроили виртуальную машину Kali. Создайте нового пользователя.
```
sudo useradd -m w4sp-lab -s /bin/bash -G sudo -U
```
4. Установите пароль
```
passwd w4sp-lab
```
5. Выйдите из системы и перейдите на пользователя w4sp-lab, затем загрузите настоящую лабораторную среду.
Перейдите в папку загрузок, а затем в загруженную директорию.
Вначале установите программы, необходимые для работы.
```
sudo apt install -y python3-docker
sudo apt install wireshark net-tools ethtool xterm
```
6. Теперь самая важная часть. Это займет много времени, и это будет выглядеть так, как будто загрузка зависла, но не убивайте процесс и просто подождите.
```
sudo python3 w4sp_webapp.py
```
7. После загрузки всех изображений браузер может открываться автоматически, а может и не открываться. Не паникуйте. Откройте вкладку Firefox или hromium  и введите этот адрес.
```
http://127.0.0.1:5000
```
8. Лаборатория должна появиться. Нажмите на кнопку SETUP. 
9. ВНИАНИЕ! Возмоно, произойдет сбой. Извините, но теперь вам просто нужно ввести еще несколько команд, чтобы все заработало.
Убейте процесс, закройте вкладку. Затем в терминале
```
sudo usermod -aG docker w4sp-lab
sudo systemctl enable docker
```
10. Теперь снова запустите скрипт Python
```
sudo python3 w4sp_webapp.py
```
11. Введите в браузере
```
http://127.0.0.1:5000
```
12. Нажмите кнопку SETUP.
Ваша лаборатория запущена и работает.
