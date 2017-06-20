# shorturl
短链接

生成思路：

1.将"原始链接（长链接）+key(自定义字符串,防止算法泄漏)"MD5加密

2.把加密字符按照 8 位一组 16 进制与 0x3FFFFFFF 进行位与运算，把得到的值与 0x0000003D 进行位与运算，取得字符数组 chars 索引，把取得的字符相加，每次循环按位右移 5 位，把字符串存入对应索引的输出数组(4组6位字符串)

3.生成4以下的随机数，从输入数组中取出随机数对应位置的字符串，作为短链，存入数据库或者NoSql