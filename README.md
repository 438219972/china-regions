# china-regions
## 中国五级行政区域地址库(China 's five - level administrative region)


这是一个五级地址库，包含742457条记录，精确的村及门牌，表结构如下：

```sql
CREATE TABLE
    earea5_
    (
        id_ VARCHAR(16) NOT NULL COMMENT '主键',
        date_created_ DATETIME(6) NOT NULL COMMENT '最初创建时间',
        disabled_ DECIMAL(1,0) NOT NULL COMMENT '是否有效',
        last_updated_ DATETIME(6) NOT NULL COMMENT '最后更新时间',
        version_ INT NOT NULL COMMENT '乐观锁版本号',
        code_ VARCHAR(16) NOT NULL COMMENT '行政代码',
        lat_ DECIMAL(19,8) COMMENT '纬度',
        level_ SMALLINT NOT NULL COMMENT '层级',
        lng_ DECIMAL(19,8) COMMENT '经度',
        merger_name_ VARCHAR(255) COMMENT '组合名称',
        name_ VARCHAR(50) COMMENT '名称',
        pinyin_ VARCHAR(255) COMMENT '拼音',
        short_name_ VARCHAR(255) COMMENT '简称',
        tel_code_ VARCHAR(255) NOT NULL COMMENT '电话区号',
        zip_code_ VARCHAR(255) NOT NULL COMMENT '邮政编码',
        parent_id_ VARCHAR(255),
        PRIMARY KEY (id_),
        CONSTRAINT fktgdyxr8dq43ywpx90s1axc9nw_ FOREIGN KEY (parent_id_) REFERENCES `earea5_`
        (`id_`),
        INDEX fktgdyxr8dq43ywpx90s1axc9nw_ (parent_id_)
    )
    ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='五级区域表';
```
