atom/group
1. 测试库： rm-wz9h5hd1d1a8c7886o.mysql.rds.aliyuncs.com (qatest_normal_0,qatest_normal_1,qatest_normal_2)
2. 创建脚本
-- (1).建库:
CREATE DATABASE `qatest_normal_0`;
CREATE DATABASE `qatest_normal_1`;
CREATE DATABASE `qatest_normal_2`;

CREATE DATABASE `qatest_normal_0_bac`;
CREATE DATABASE `qatest_normal_1_bac`;
CREATE DATABASE `qatest_normal_2_bac`;

-- (2).在库中建表normaltbl_0001
USE qatest_normal_0;
CREATE TABLE `normaltbl_0001` (
`pk` int(11) NOT NULL,
`id` int(11) DEFAULT NULL,
`gmt_create` date DEFAULT NULL,
`name` varchar(30) DEFAULT NULL,
`floatCol` float(9,3) DEFAULT 0.000,
PRIMARY KEY (`pk`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

USE qatest_normal_1;
CREATE TABLE `normaltbl_0001` (
`pk` int(11) NOT NULL,
`id` int(11) DEFAULT NULL,
`gmt_create` date DEFAULT NULL,
`name` varchar(30) DEFAULT NULL,
`floatCol` float(9,3) DEFAULT 0.000,
PRIMARY KEY (`pk`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

USE qatest_normal_2;
CREATE TABLE `normaltbl_0001` (
`pk` int(11) NOT NULL,
`id` int(11) DEFAULT NULL,
`gmt_create` date DEFAULT NULL,
`name` varchar(30) DEFAULT NULL,
`floatCol` float(9,3) DEFAULT 0.000,
PRIMARY KEY (`pk`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

USE qatest_normal_0_bac;
CREATE TABLE `normaltbl_0001` (
`pk` int(11) NOT NULL,
`id` int(11) DEFAULT NULL,
`gmt_create` date DEFAULT NULL,
`name` varchar(30) DEFAULT NULL,
`floatCol` float(9,3) DEFAULT 0.000,
PRIMARY KEY (`pk`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

USE qatest_normal_1_bac;
CREATE TABLE `normaltbl_0001` (
`pk` int(11) NOT NULL,
`id` int(11) DEFAULT NULL,
`gmt_create` date DEFAULT NULL,
`name` varchar(30) DEFAULT NULL,
`floatCol` float(9,3) DEFAULT 0.000,
PRIMARY KEY (`pk`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

USE qatest_normal_2_bac;
CREATE TABLE `normaltbl_0001` (
`pk` int(11) NOT NULL,
`id` int(11) DEFAULT NULL,
`gmt_create` date DEFAULT NULL,
`name` varchar(30) DEFAULT NULL,
`floatCol` float(9,3) DEFAULT 0.000,
PRIMARY KEY (`pk`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- (3).在库创建tddl用户,授予读写数据库权限
CREATE USER 'tddl'@'%' IDENTIFIED BY 'tddl';
GRANT Insert,Update,Select,Delete ON qatest_normal_0.* TO 'tddl'@'%';
GRANT Insert,Update,Select,Delete ON qatest_normal_1.* TO 'tddl'@'%';
GRANT Insert,Update,Select,Delete ON qatest_normal_2.* TO 'tddl'@'%';
GRANT Insert,Update,Select,Delete ON qatest_normal_0_bac.* TO 'tddl'@'%';
GRANT Insert,Update,Select,Delete ON qatest_normal_1_bac.* TO 'tddl'@'%';
GRANT Insert,Update,Select,Delete ON qatest_normal_2_bac.* TO 'tddl'@'%';

matrix
1. 测试库： mysql -h10.232.24.104 -udiamond -pdiamond

oceanbase
1. 测试库:  mysql -h10.235.152.7 -uadmin -padmin -P2828


tddl-server
1. 测试库 
	mysql -h127.0.0.1 -uandor_mysql_qatest -p123456 -P8507

2. 体验环境	
	mysql -h10.235.170.41 -ucorona_qatest -pcorona_qatest -P8507
	mysql -h10.235.170.41 -uandor_mysql_qatest -p123456 -P8507