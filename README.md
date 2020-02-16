# Ax2009 DotNetFramework 4 Support
Add .NET Framework 4 support to Ax2009

По мотивам http://axforum.info/forums/showthread.php?p=413479#post413479

АОС и клиент аксапты по умолчанию работают только с .NET Framework 3.5.
Чтобы из программного кода можно было обращаться к .NET Framework более высоких версий - нужно внести следующие изменения :
- в каталог `Bin` АОСа скопировать файл `AOS-Bin\Ax32Serv.exe.config`
- в каталог `Bin` клиента скопировать файл `Client-Bin\Ax32.exe.config`
И перезапустить АОС.

Содержимое файлов :
```
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <startup useLegacyV2RuntimeActivationPolicy="true">
       <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
</configuration>
```

Если атрибут `supportedRuntime/@sku` будет содержать более высокую версию чем версия .NET Framework на текущей машине, то АОС и клиент при запуске выдадут ошибку.
