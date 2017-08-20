#fb-group-crawler

##Facebook Group Crawler

[fb-hfc](https://github.com/prili/fb-hfc)它有看的權利。
我發現它只適用於Ubuntu和OSX。

## 安裝

``` bash
apt-get install python-lxml
pip install -r requirements.txt
```

## 執行

### 直接執行

```python
python fb-hfc.py -username '<username>'  -password '<password>' -query '<graph search query>' -group <name=url=id>
```

username: Facebook ID
password: Facebook PW
query : Member
group : 組別名=組地址=組ID

組ID [Lookup-ID](http://lookup-id.com)你可以使用一個調用的站點。

### Shell穿過

```bash
#!/bin/bash

username=
password=

cat ./source/group_list.txt | \
while read line
do
	echo -e "\n\n\n $line"
	python fb-crawler.py -username $username -password $password -query member -group $line

    pids=$(pidof /usr/bin/Xvfb)
	echo "Xvfb pids : $pids"
	kill $pids
	ps
done
```

username: Facebook ID
password: Facebook PW

在頂部輸入值後，子文件夾源中的組列表

	name=url=id
	name=url=id

如下圖所示。

## 餘量

會員人數 8000~9000對於主組，數據不准確, 9000擁有多個人的群組無法獲取更多數據。
