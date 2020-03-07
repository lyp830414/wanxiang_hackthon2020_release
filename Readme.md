# 《疫情别链》项目

   - 项目主旨以社区房屋登记和租房合同管理治理为抓手，发挥以房盯人，按人控疫情为主要社区治理手段和措施，
发挥区块链技术的资产溯源专长，协助本次疫情的社区业主和外来人员管控，生活服务支持和复工复产人员管理，
同时为疫情后的基层社区管理做好基础。
通过实施零知识证明的数据隐私计算方案，对租房登记管理，承租人的信息，疫情治理信息保护进行加强。
发挥区块链资产溯源的特点，对守法用户的信用积分奖励，鼓励社区人人参加治理，对违法行为的群防群治，
违法证据及时取证上区块链系统备案，对违规人员的信用积分处罚等治理规则。
采用基于FPGA的零知识证明硬件加速卡方案来加速隐私计算的效率和系统整体性能，达到更好的用户体验。

   - 本次项目DEMO主要演示了如何利用零知识证明对链上数据进行零知识证明进行加解密，从而为用户的原始数据信息进行确权和防伪。
该DEMO分为中英文两个版本，采用python3进行开发和测试。使用方法和日志信息如下所示。

## 本项目负责成员

- 队长：徐鹤军
- 队员：李乙平

## 项目操作演示

```
======================================= 
=            环境预装要求	      =
======================================= 

- Ubuntu 18.X LTS

- Ipfs server 
       
       snap search ipfs && snap install ipfs && sudo snap run ipfs daemon

- ipfshttpclient

       pip3 install ipfshttpclient --user -i https://mirrors.aliyun.com/pypi/simple

- python3.x


=======================================     
=      中文版操作过程和信息日志	      =
=======================================

注：交互部分选择YES则会打印生成的零知识证明文件内容。为节约篇幅本例选No。


lyp830414@lyp830414-JASPER12:~/wanxiang_hackthon2020_release$ python3 lyp_ipfs_http_client_sample3.py 

++++ 步骤 1. 上传文件test.txt 到 IPFS....

上传完毕.

文件: test.txt
   - md5  Hash d990a51527cf408564acdb18b465a4b3: 
   - ipfs Hash QmR4frR4bhXVZfWkPhMGSSMGjDogg3SabEe7dN3ufL2GmV: 
文件内容:  b'New Test String\n'

文件内容准备完成（如上所示）。数据长度: 123
data1 = {
                   "file": [
                      {
                        "md5_hash": d990a51527cf408564acdb18b465a4b3,
                        "ipfs_hash": QmR4frR4bhXVZfWkPhMGSSMGjDogg3SabEe7dN3ufL2GmV
                      }
                    ]
                  }           
              

++++ 步骤 2. 根据上述数据产生你的零知识证明数据ZK1....

ZK1 生成完毕.

ZK1 的数据长度: 11602

--你是否愿意查看ZK1 数据的原始数据部分? [yes/no]n

好的.跳过.


++++ 步骤 3. 用第一阶段零知识证明ZK1 数据产生你的下一个零知识证明ZK2 数据....


ZK2 所需的原始数据部分如下所示. 数据长度: 11701
data2 = {   
                   "zk1": <zk1>,
                   "zk2": [
                     {
                       "md5_hash": d990a51527cf408564acdb18b465a4b3,
                       "add_time": 1583568798.773857
                     }
                   ]
                }
               

为产生零知识证明ZK2 所需的数据准备完毕.数据长度: 11602
ZK2 生成完毕.

ZK2 数据长度: 1105694

--你是否愿意查看ZK2 数据的原始数据部分? [yes/no]n

好的.跳过.


++++ 步骤 4. 用零知识证明数据 ZK1 和 ZK2 来产生你的验证文件file_zk.txt....

文件已产生.

你的file_zk.txt 数据格式如下(如有需要,请打开和查看此文件的原始数据):

test.txt

<zk1>

<zk2>


++++ 步骤 5. 上传你的file_zk.txt 文件到IPFS....

上传完毕.

文件: test.txt
   - md5  Hash: d990a51527cf408564acdb18b465a4b3
   - ipfs Hash: QmR4frR4bhXVZfWkPhMGSSMGjDogg3SabEe7dN3ufL2GmV
文件内容:  b'New Test String\n'

++++ 步骤 6. 用file_zk.txt 验证你的文件test.txt 的正确性....

验证完毕.

文件内容:  {'file': [{'md5_hash': 'd990a51527cf408564acdb18b465a4b3', 'ipfs_hash': 'QmR4frR4bhXVZfWkPhMGSSMGjDogg3SabEe7dN3ufL2GmV'}]}

========================== 本次Demo 演示完成. 感谢您的参与 ============================

lyp830414@lyp830414-JASPER12:~/wanxiang_hackthon2020_release$ 




=======================================     
=      英文版操作过程和信息日志	      =
=======================================

注：交互部分选择YES则会打印生成的零知识证明文件内容。为节约篇幅本例选No。


lyp830414@lyp830414-JASPER12:~/wanxiang_hackthon2020_release$ python3 lyp_ipfs_http_client_sample2.py 

++++ Step 1. Send file test.txt to IPFS....

Done.

File: test.txt
   - md5  Hash d990a51527cf408564acdb18b465a4b3: 
   - ipfs Hash QmR4frR4bhXVZfWkPhMGSSMGjDogg3SabEe7dN3ufL2GmV: 
File Content:  b'New Test String\n'

File data prepared as following. Len of data: 123
data1 = {
                   "file": [
                      {
                        "md5_hash": d990a51527cf408564acdb18b465a4b3,
                        "ipfs_hash": QmR4frR4bhXVZfWkPhMGSSMGjDogg3SabEe7dN3ufL2GmV
                      }
                    ]
                  }           
              

++++ Step 2. Generate your ZK1 with prepared data above....

NOW CREATE: data len:  123
NOW CREATE END
Done.

len of ZK1 data: 11206

--Do you want to view the raw data of ZK1 ? [yes/no]n

Ok skip.


++++ Step 3. Generate your ZK2 with ZK1....


File data prepared as following. Len of data: 11305
data2 = {   
                   "zk1": <zk1>,
                   "zk2": [
                     {
                       "md5_hash": d990a51527cf408564acdb18b465a4b3,
                       "add_time": 1583567115.571205
                     }
                   ]
                }
               

ZK1 data prepared for ZK: Len of data: 11206
NOW CREATE: data len:  11305
NOW CREATE END
Done.

len of ZK2 data: 1030004

--Do you want to view the raw data of ZK2 ? [yes/no]n

Ok skip.


++++ Step 4. Generate your file_zk.txt file with ZK1 and ZK2....

Done.

Your file_zk.txt data(Please check the file raw_data if need):

test.txt

<zk1>

<zk2>


++++ Step 5. Upload your file_zk.txt file to IPFS....

Done.

File: test.txt
   - md5  Hash: d990a51527cf408564acdb18b465a4b3
   - ipfs Hash: QmR4frR4bhXVZfWkPhMGSSMGjDogg3SabEe7dN3ufL2GmV
File Content:  b'New Test String\n'

++++ Step 6. Verify your file test.txt with file_zk.txt....

ZK1 before: len: 11206
OK, we got len new zk1: 11206
Done.

File Content:  {'file': [{'md5_hash': 'd990a51527cf408564acdb18b465a4b3', 'ipfs_hash': 'QmR4frR4bhXVZfWkPhMGSSMGjDogg3SabEe7dN3ufL2GmV'}]}

========================== OK. Demo end. Thank you ============================
```
