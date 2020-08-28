# addmember-telegram
Add member auto to telegram group

Note: need about 20 accounts to run

## How to set this up on your server

### Install dependencies
```
sudo apt-get update
sudo apt-get install python3.6
sudo apt install python3-pip
pip install Telethon==0.12
pip install TgCrypto
```

### Setting this up
1. Clone this repository and add permission
```
git clone https://github.com/getdzypher/addmember-telegram tgadd
chmod -R 755 tgadd
```
2. Go to the cloned repository "tgadd"
```
cd tgadd
```
3. Create config.json and phone.txt
```
cp config.example.json config.json
cp phone.example.json phone.json
```
4. Edit your configuration

+ create app in https://my.telegram.org/apps and have api_id, api_hash
```
{
	"group_target": YOUR_GROUP_ID,
	"group_source": YOUR_SCRAPE_GROUP_ID,
	"accounts": [
		{
			"phone": "+7900000", //change this
			"api_id": 1670651, //change this
			"api_hash": "fa61ee714bc8cd6dfb80edcd354ef2a2" //change this
		}
	]
}
```
5. Run session
```
python 3 init_session.py
```

# Features
### init session
run init session to create session for on phone
```
python 3 init_session.py
```

### create phone.txt

create phone.txt have format same phone.example.txt
phone;api_id;api_hash
```
cp phone.example.json phone.json
```

### getdata.py

+ get groups, users in group and save folder data
```
python 3 getdata.py
```

### get_data.py

+ new update get groups, users in group and save folder data
```
python 3 get_data.py
```

### getdataonlyphone.py

+ get data for phone only
```
python 3 getdataonlyphone.py
```

### addmember.py
change id group source, target, base on file data/group/+84....csv (need upgrade in the future)

group_target_id = 1331409327
group_source_id = 1166894130
```
python 3 addmember.py
```
