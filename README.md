# mobile2city中国手机号转换城市
* CityInfo:332行
* CityMobile:216064行

###mssql
```sql
CREATE TABLE [CityInfo] (
    [CityCode] varchar(4) NOT NULL,
    [CityName] nvarchar(50) Default (N'''') NOT NULL,
    [ProvinceCode] int Default 0 NOT NULL,
    [Province] nvarchar(50) Default (N'''') NOT NULL,
    PRIMARY KEY ([CityCode])
);
CREATE TABLE [CityMobile] (
    [Mobile] varchar(7) NOT NULL,
    [CityCode] varchar(4) Default (N'''') NOT NULL,
    [CityName] nvarchar(50) Default (N'''') NOT NULL,
    [ProvinceCode] int Default 0 NOT NULL,
    [Province] nvarchar(50) Default (N'''') NOT NULL,
    [CstCode] int Default 0 NOT NULL,
    [PostCode] varchar(6) Default (N'''') NOT NULL,
    PRIMARY KEY ([Mobile])
);
```
###mysql
```sql
CREATE TABLE `CityInfo` (
    `CityCode` varchar(4) NOT NULL COMMENT '区号编号',
    `CityName` varchar(50) Default "\'" NOT NULL COMMENT '区名称',
    `ProvinceCode` int Default 0 NOT NULL COMMENT '省份编号',
    `Province` varchar(50) Default "\'" NOT NULL COMMENT '省份',
    PRIMARY KEY (`CityCode`)
);
CREATE TABLE `CityMobile` (
    `Mobile` varchar(7) NOT NULL COMMENT '手机号前7位',
    `CityCode` varchar(4) Default "\'" NOT NULL COMMENT '区号',
    `CityName` varchar(50) Default "\'" NOT NULL COMMENT '区名',
    `ProvinceCode` int Default 0 NOT NULL COMMENT '省份编号',
    `Province` varchar(50) Default "\'" NOT NULL COMMENT '省份',
    `CstCode` int Default 0 NOT NULL COMMENT '运营商编号',
    `PostCode` varchar(6) Default "\'" NOT NULL COMMENT '邮编',
    PRIMARY KEY (`Mobile`)
);
```
###sqlite
```sql
CREATE TABLE "CityInfo" (
    "CityCode" TEXT(4) NOT NULL,
    "CityName" TEXT(50) Default "'" NOT NULL,
    "ProvinceCode" INTEGER Default 0 NOT NULL,
    "Province" TEXT(50) Default "'" NOT NULL,
    PRIMARY KEY ("CityCode")
);
CREATE TABLE "CityMobile" (
    "Mobile" TEXT(7) NOT NULL,
    "CityCode" TEXT(4) Default "'" NOT NULL,
    "CityName" TEXT(50) Default "'" NOT NULL,
    "ProvinceCode" INTEGER Default 0 NOT NULL,
    "Province" TEXT(50) Default "'" NOT NULL,
    "CstCode" INTEGER Default 0 NOT NULL,
    "PostCode" TEXT(6) Default "'" NOT NULL,
    PRIMARY KEY ("Mobile")
);
```
###oracle
```sql
CREATE TABLE CityInfo (
    CityCode varchar2(4) NOT NULL,
    CityName nvarchar2(50) Default '''' NOT NULL,
    ProvinceCode NUMBER(10) Default 0 NOT NULL,
    Province nvarchar2(50) Default '''' NOT NULL,
    PRIMARY KEY (CityCode)
);
CREATE TABLE CityMobile (
    Mobile varchar2(7) NOT NULL,
    CityCode varchar2(4) Default '''' NOT NULL,
    CityName nvarchar2(50) Default '''' NOT NULL,
    ProvinceCode NUMBER(10) Default 0 NOT NULL,
    Province nvarchar2(50) Default '''' NOT NULL,
    CstCode NUMBER(10) Default 0 NOT NULL,
    PostCode varchar2(6) Default '''' NOT NULL,
    PRIMARY KEY (Mobile)
);
```
###access
```sql
CREATE TABLE [CityInfo] (
    [CityCode] text(4) NOT NULL,
    [CityName] text(50) Default "'",
    [ProvinceCode] int Default 0,
    [Province] text(50) Default "'",
    PRIMARY KEY ([CityCode])
);
CREATE TABLE [CityMobile] (
    [Mobile] text(7) NOT NULL,
    [CityCode] text(4) Default "'",
    [CityName] text(50) Default "'",
    [ProvinceCode] int Default 0,
    [Province] text(50) Default "'",
    [CstCode] int Default 0,
    [PostCode] text(6) Default "'",
    PRIMARY KEY ([Mobile])
);
```

###工具
```
git clone https://github.com/LiveXY/mobile2city.git
cd mobile2city/
npm install && npm link

mobile2city 13701862737 13703762738
#13701862737 : 0210 200000 上海 上海
#13703762738 : 0376 465150 河南 潢川

ip2address '125.42.204.47;125.42.204.45;61.53.186.5;125.42.204.46;222.73.202.202'
#  125.42.204.47 : 河南省 信阳市  { y: '3757267.65', x: '12700076.95' } baidu
#  125.42.204.45 : 中国 河南省 信阳市  taobao
#    61.53.186.5 : 中国 河南省 平顶山市  taobao2
#  125.42.204.46 : 中国 河南 信阳  ipip
# 222.73.202.202 : 中国 上海 上海  sina
ip2address baidu '125.42.204.47;125.42.204.45;61.53.186.5;125.42.204.46;222.73.202.202'
```