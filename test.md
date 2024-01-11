| 函数名| 描述| 参数| 配置示例| 脱敏前数据| 脱敏后数据|
| ------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------- | ----------------------- | ---------------------------------------------------------------- |
| LaplaceDPFloat64| differential privacy masking based on laplace| 1: l0sensitivity, 2: lInfSensitivity, 3: epsilon, 4: delta| LaplaceDPFloat64,100,1,1,0| 3200.53| 3074.3990583359264|
| LaplaceDPInt64| differential privacy masking based on laplace| 1: l0sensitivity, 2: lInfSensitivity, 3: epsilon, 4: delta| LaplaceDPInt64,100,1,1,0.5| 3200| 3198|
| FF1| 格式保留加密, ff1 algorithm| 1: radix(default 10, max size 62, min size 2, [0-9a-zA-Z]), 2: key, 3: tweak| FF1,10| 123| 009|
| FF3| 格式保留加密, ff3 algorithm| 1: radix(default 10, max size 62, min size 2, [0-9a-zA-Z]), 2: key, 3: tweak| FF3,10| 123| 080|
| Base64| base64加密|| Base64| abc| YWJj|
| DES| des 加密| 1: key, 2: iv| DES| hello world| jZLr1ir1An0IQc30XbLL3A==|
| AES| aes 加密| 1: key, 2: iv| AES| hello world| F5QMumnZOlCchKi2nu99rA==|
| TDEA| tdea 加密| 1: key, 2: iv| TDEA| hello world| F0HMxhk+uKKBSlR1IAyt+Q==|
| AESCTR| aesctr 加密| 1: key, 2: iv| AESCTR| hello world| 0URdmXIvWjcZS3U=|
| RSA| rsa 加密|| RSA| hello world| ... ...|
| ECC| ecc 加密|| ECC| hello world| ... ...|
| Fake| 生成不同类型的假数据| 1: type(name, address, license-plate, email, ssn, birthday, creditcard, url, number, uuid, ip, ipv6) | Fake,Name| Any string| Auto generate fake string|
| CRC32| crc32 hash|| CRC32| abc| 352441c2|
| MD5| md5 hash|| MD5 | abc | 900150983cd24fb0d6963f7d28e17f72 |
| SHA1| sha1 hash|| SHA1| abc | a9993e364706816aba3e25717850c26c9cd0d89d |
| SHA2| sha2 hash|| SHA2| abc | ba7816bf8f01cfea414140de5dae2223b00361a396177a9cb410ff61f20015ad |
| HMAC| hmac hash| 1: hash function. e.g., md5, sha1, sha2| HMAC,md5,"pass" | hello world | 37c4d226765f06daa3ad91a6c33a5d3e |
| Mangle| 语料库脱敏函数| 1: corpus name, 2. secret| Mangle,"en_US","secret password"| hello world!| spars dream! |
| Phone | 手机号脱敏函数|| Phone | 13000000123 | 130*****123|
| Mail| 邮箱脱敏函数 || Mail| zhangsan001@d18n.com| z**********@*******m |
| Username| 用户名脱敏函数 || Username| Dave Li | D******|
| Domain| 域名脱敏函数 || Domain| example.com | e*********m|
| CreditCard| 银行卡脱敏函数|| CreditCard| 6227612145830440| 62276121****0440 |
| PersonalID| 个人id脱敏函数|| PersonalID| 110223700003697 | 110223*****3697|
| USCC| 社会信用号脱敏函数|| USCC| 71797173LM37QP0D4H| 717971********0D4H |
| Age | 年龄取底|| Age | 46| 40 |
| Birthday| 生日脱敏函数|| Birthday| 2020-05-34| NNNN-NN-NN |
| IP| ip脱敏函数|| IP| 192.168.0.1 | 127.0.0.1|
| Password| 密码脱敏函数|| Password| asfa@12323ssda| *********|
| Salary| 工资脱敏函数|| Salary| 1350| 1000 |
| LicensePlate| 车牌号脱敏函数|| LicensePlate| 鄂D71D44| 鄂****4|
| OrganizationCode| 组织号脱敏函数|| OrganizationCode| 100000439 | 100****439 |
| Shuffle | 洗牌函数 | 1. corpus name. e.g., 0-9, Lower, Upper, Chinese | Shuffle | 1234567890| 4802731596 |
| ShuffleRight| 右侧洗牌函数 | 1. index | ShuffleRight,4| 1234567890| 1234731596 |
| ShuffleLeft | 左侧洗牌函数| 1. index | ShuffleLeft,4 | 1234567890| 4802737890 |
| Rot | 数据混淆函数 | 1. radix. e.g., 47, 18, 13, 5, 32768 | Rot,5 | 1234567890| 6789012345 |
| Morse | 摩斯码 || Morse | def | .- -... -.-. |
| Caesar| 凯撒密码 | 1. index | Caesar,3| abc | def|
| Smoke | 数据替换 | 1. replacement | Smoke,"\*"| 123 | \*\*\* |
| SmokeLeft | 替换左侧数据| 1. index, 2. replacement | SmokeLeft,2,"\*"| 123 | \*\*3|
| ReserveLeft | 保留左侧替换右侧 | 1. index, 2. replacement | ReserveLeft,2,"\*"| 123 | 12\* |
| SmokeRight| 替换右侧数据 | 1. index, 2. replacement | SmokeRight,2,"\*" | 123 | 1\*\*|
| ReserveRight| 保留右侧替换左侧 | 1. index, 2. replacement | ReserveRight,2,"\*" | 123 | \*23 |
| SmokeMargin | 替换中间| 1. index, 2. replacement | SmokeMargin,2,"\*"| 123456| \*\*34\*\* |
| ReserveMargin | 保留中间 | 1. index, 2. replacement | ReserveMargin,2,"\*"| 123456| 12\*\*56 |
| SmokeOuter| 替换两侧 | 1. left index, 2. right index, 3. replacement| SmokeOuter,2,1,"\*" | 123456| \*\*345\*|
| ReserveOuter| 保留两侧| 1. left index, 2. right index, 3. replacement| ReserveOuter,2,1,"\*" | 123456| 12***6 |
| SmokeInner| 替换左右侧中间的部分 | 1. left index, 2. right index, 3. replacement| SmokeInner,2,1,"\*" | 123456| 12***6 |
| ReserveInner| 保留左右侧中间的部分| 1. left index, 2. right index, 3. replacement| ReserveInner,2,1,"\*" | 123456| \*\*345\*|
| SmokeCharLeft | 替换特殊字符左侧| 1. index, 2. replacement | SmokeCharLeft,"@","\*"| zhangsan123@example.com | ***********@example.com|
| SmokeCharRight| 替换特殊字符右侧| 1. index, 2. replacement | SmokeCharRight,"@","\*" | zhangsan123@example.com | zhangsan123@***********|
| Replace | 字符串替换 | 1. old string, 2. replacement, 3. n(-1 for all)| Replace,2,"\*",-1,"\*"| 123 | 1\*3 |
| RegexpReplace | 使用字符串替换| 1. regexp, 2. replacement| RegexpReplace,"[bc]","*"| abcdef| a\*\*def |
| RegexpRandomReplace | 使用正则随机替换 | 1. regexp, 2. min, 3. max| RegexpRandomReplace,"^1[3-9][\\d]{9}\$",5,10| 13782430405 | 13614299600|
| Reverse | 字符串逆转 || Reverse | abc | cba|
| ToUpper | 字符串大写|| ToUpper | abc | ABC|
| ToLower | 字符串小写|| ToLower | ABC | abc|
| Const | 使用常量替换| 1. replacement | Const,"MASKED"| abc | MASKED |
| Number2Const| 使用常量替换所有| 1. replacement, default 9| Number2Const| (+086)130-1234-123| (+999)999-9999-999 |
| Char2Const| 使用常量替换所有字符| 1. replacement, default N| Char2Const| abc-def | NNN-NNN|
| NumberFloor | 数字取底 | 1. index | NumberFloor,2 | 123.23| 100|
| DateRound | 日期省略 | 1. data format, 2. accuracy: second, minute, hour(default), day, month, year | DateRound,hour| 2021-07-23 17:26:45 | 2021-07-23 17:00:00|
| Dateformat| 日期格式转换| 1.old date format2.new date format | dateformat,"YYYY-MM-DD HH:mm:ss", "YYYY/MM/DD HH-mm-ss" | 2021-07-23 17:26:45 | 2021/07/23 17-26-45|
| LoopMoveLeft| 循环左移 | 1. index | LoopMoveLeft,3| abcdefg | defgabc|
| LoopMoveRight | 循环右移| 1. index | LoopMoveRight,3 | abcdefg | efgabcd|
| TruncateLeft| 移除左侧 | 1. index | TruncateLeft,2| abcdef| ef |
| TruncateRight | 移除右侧| 1. index | TruncateRight,2 | abcdef| ab |
| Abbreviate| 字符串缩写 || Abbreviate| strategy-limited| stg-ltd|
| Initialism| 首字母缩略 || Initialism| hello world | hw |
| Numeronym | 数据省略|| Numeronym | internationalization| i18n |
| SM2 | SM2 algorithm|| SM2 | hello world | ... ...|
| SM3 | SM3 algorithm|| SM3 | hello world | ... ...|
| SM4 | SM4 algorithm|| SM4 | hello world | b9b1742de155fe5720c0b8b1b95e3134 |
