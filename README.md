# NSFOCUS_RSAS_connector
用原生requests写成的绿盟扫描器调用接口

===使用方法===
1. 打开目录下的config.ini，将用户名，密码，扫描器地址（带协议的完整URL，如：https://1.1.1.1）分别填好
2. 如果使用主机+弱口令扫描，打开目录下ip.txt将要扫描的IP放进去；如果使用web扫描，打开目录下url.txt将要扫描的url放进去
3. 主机扫描不会自动拆分IP建立任务，单次最大IP数量为65535个；web扫描会将全部URL拆分成若干任务，每个任务会有后缀<拆分xx>
4. -n <任务名称>
5. -m <扫描模式 参数为1时是主机+弱口令扫描 参数为2时是web扫描>
6. -c <定时执行，选填参数>

PS：请cd到项目路径下打开cmd执行文件

实例：

`lvmeng_connector.exe -n "测试任务 2333" -m 1`
     
`lvmeng_connector.exe -n "测试任务 2333" -m 2 -c "08:00-12:00"`
