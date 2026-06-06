
```markdown
# تثبيت نظام Kali Linux على Termux

## المتطلبات:
- 1 كيكا (1GB) رام
- 2 كيكا (2GB) تخزين
- تطبيق Termux
- عارض RVNC
- اتصال بالإنترنت

## الخطوات:

1. تحديث الحزم:
   ```sh
   pkg update
   pkg install openssl-tool
   ```

2. تثبيت حزمة wget:
   ```sh
   pkg install wget
   ```

3. تثبيت حزمة Kali Linux:
   ```sh
   wget -O install-nethunter-termux https://offs.ec/2MceZWr
   chmod +x install-nethunter-termux
   shell
   ./install-nethunter-termux
   ```

4. اختيار نوع الأداء:
   - اختر النوع المطلوب: NetHunter ARM64 (full/minimal/nano)

5. انتظر حتى يتم تحميل وتثبيت النظام.

6. عندما يطلب منك حذف الملفات، اختر "N".

7. انتظر قليلاً حتى يتم فك الضغط وتحميل ال rootfs.

8. اكتب الأمر `nethunter` للدخول إلى نظام Kali Linux.

9. إذا أردت واجهة رسومية، قم بتثبيت RVNC واتبع الخطوات المذكورة.

10. لحل مشكلة "[Process completed (signal 9) - press Enter]"، قم بتنفيذ الأوامر التالية:
    ```sh
    apt install android-tools
    adb
    adb pair Yor_Ip
    adb shell "/system/bin/dumpsys activity settings | grep max_phantom_processes"
    adb shell "/system/bin/dumpsys activity processes -a"
    adb shell "/system/bin/device_config set_sync_disabled_for_tests persistent"
    adb shell "/system/bin/device_config put activity_manager max_phantom_processes 2147483647"
    adb shell settings put global settings_enable_monitor_phantom_procs false
    ```

11. قم بتشغيل Termux واكتب الأمر `nh` ثم `nethunter kex`.

12. انتقل إلى تطبيق RVNC واتبع الخطوات المذكورة للاتصال بنظام Kali Linux.

مبروك! لقد قمت بتثبيت نظام Kali Linux بنجاح على جهازك باستخدام Termux.
```

هذا يشرح الخطوات بشكل أفضل ويصحح الأخطاء التي تم اكتشافها، بالإضافة إلى تنسيقه كملف `README.md` لرفعه في مستودع المشروع على منصة GitHub أو 
