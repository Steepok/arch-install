📥 Arch Linux Minimal Install Script

Полностью автоматизированный Bash-скрипт для быстрой установки чистого Arch Linux с разметкой GPT, EFI-загрузчиком и готовым пользователем user.
📄 Описание

Этот скрипт автоматически:

    Очищает диск /dev/vda

    Делает GPT-разметку с EFI, SWAP, ROOT, HOME

    Форматирует диски

    Устанавливает базовую систему base linux linux-firmware

    Создаёт пользователя user

    Настраивает sudo

    Настраивает GRUB

    Включает службы: NetworkManager, dbus-broker

    Перезагружает систему автоматически

💿 Разметка диска /dev/vda
Раздел	Размер	Назначение	Файловая система	Монтирование
vda1	512MB	EFI	FAT32	/efi
vda2	5.5GB	Swap	Swap	swap
vda3	25GB	Root	ext4	/
vda4	Остальное	Home	ext4	/home
🚀 Установка
1️⃣ Загрузись в Arch ISO.
2️⃣ Скачай скрипт:

wget https://raw.githubusercontent.com/Steepok/arch-install/main/install-arch.sh
chmod +x install-arch.sh

3️⃣ Запусти установку:

./install-arch.sh

📂 Что будет после запуска:

    Всё установится полностью.

    Скрипт сам выполнит umount -R /mnt.

    Через 5 секунд произойдёт автоматическая перезагрузка.

    После перезагрузки залогинься под user.

🔑 Пароли

В процессе установки тебе нужно будет самому задать пароль для root и user.
🖥 Примеры включённых служб:

systemctl enable NetworkManager
systemctl enable dbus-broker

⚙️ Что делать после первого запуска

Зайдя в систему, рекомендуется:

sudo systemctl enable --now systemd-timesyncd

🏁 Готово! У тебя минимальный, чистый, современный Arch Linux.
