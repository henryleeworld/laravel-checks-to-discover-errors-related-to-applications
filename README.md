# Laravel 8 檢查發現應用程式相關的錯誤

引入 imanghafoori 的 laravel-microscope 套件來擴增檢查發現應用程式相關的錯誤，幫助發現應用程式中可能沒有太多測試的錯誤和陷阱；然而，這個套件對於具有許多測試案例的應用程式也很有幫助。

## 使用方式
- 把整個專案複製一份到你的電腦裡，這裡指的「內容」不是只有檔案，而是指所有整個專案的歷史紀錄、分支、標籤等內容都會複製一份下來。
```sh
$ git clone
```
- 將 __.env.example__ 檔案重新命名成 __.env__，如果應用程式金鑰沒有被設定的話，你的使用者 sessions 和其他加密的資料都是不安全的！
- 當你的專案中已經有 composer.lock，可以直接執行指令以讓 Composer 安裝 composer.lock 中指定的套件及版本。
```sh
$ composer install
```
- 產生 Laravel 要使用的一組 32 字元長度的隨機字串 APP_KEY 並存在 .env 內。
```sh
$ php artisan key:generate
```
- 你可以使用 `php artisan check:{項目}` 指令來執行檢查和運行所有檢查的特殊命令。
```sh
$ php artisan check:events
$ php artisan check:gates
$ php artisan check:views
$ php artisan check:routes
$ php artisan check:psr4 {-s|--nofix}
$ php artisan check:imports {-s|--nofix}
$ php artisan check:stringy_classes
$ php artisan check:dd
$ php artisan check:early_returns
$ php artisan check:compact
$ php artisan check:blade_queries
$ php artisan check:action_comments
$ php artisan check:bad_practices
$ php artisan check:extract_blades
$ php artisan pp:route
$ php artisan check:generate
$ php artisan check:endif
$ php artisan check:all
```

----

## 畫面截圖
![](https://i.imgur.com/AZlr2k1.png)
> 檢查 PSR-4 自動載入標準