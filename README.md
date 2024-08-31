# Swap-usage
## با این کد ها میتونین ی مقدار حافظه مجازی برای رم تهیه کنین 
### مرحله 1: ایجاد فایل swap با اندازه 2GiB
```bash
sudo fallocate -l 2G /swapfile
```
### مرحله 2: تنظیم مجوزهای مناسب برای فایل swap
```bash
sudo chmod 600 /swapfile
```
### مرحله 3: ساختن فایل swap
```bash
sudo mkswap /swapfile
```
### مرحله 4: فعال کردن فایل swap
```bash
sudo swapon /swapfile
```
## مرحله 5: افزودن فایل swap به /etc/fstab برای راه‌اندازی مجدد
```bash
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```
### مرحله 6: تنظیم اولویت swap (در صورت نیاز)
>> (ااین مرحله برای اولویت فایل دو گیگی هست )
```bash
sudo swapoff /swapfile
sudo swapon --priority 1 /swapfile
```

### مرحله 7: بررسی وضعیت حافظه و swap
```bash
free -h
```
