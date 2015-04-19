# mobile2city
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
