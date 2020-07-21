# :computer: Ms_Ubuntu18.04_Cmake
윈도우에서 우분투18.04에 파이썬 3.7과 Cmake를 깔기 (이제 언제든 다시 깔 수 있다!)<br>

:innocent:__나를 위해 쓰는 글__:innocent:<br>
윈도우 Microsoft Store에서 Ubuntu를 까는데 Ubuntu, Ubuntu 18.04 LTS, Ubuntu 20.04 LTS가 있다.<br>
Ubuntu를 깔고 했더니 `cmake build`에서 지속적인 에러가 났는데 Ubuntu 18.04에서는 잘 됐기에 <br>
다음에도 `Ubuntu 18.04`를 깔자~<br>
~~나중엔 잘 될... 수도... 있겠지만^^~~

### :point_right: pip3 설치
```
$ sudo-apt-get upgarde
$ sudo apt-get update
$ sudo apt-get install python3-pip
```
### :point_right: jupyter, numpy, pandas 설치
```
$ sudo pip3 install jupyter numpy pandas
# 주피터 노트북을 실행할 때 아래의 주소를 크롬창에 그대로 복붙
$ jupyter notebook --no-browser
```
### :point_right: python3.7 설치 or 다른 버전 변경
* ubuntu 18.04에서는 파이썬을 그냥 깔면 2.7이 깔렸는데 나는 3.7을 원하니 직접 깔아주자
```
$ sudo apt-get install -y build-essential
$ sudo apt-get install -y checkinstall
$ sudo apt-get install -y libreadline-gplv2-dev
$ sudo apt-get install -y libncursesw5-dev
$ sudo apt-get install -y libssl-dev
$ sudo apt-get install -y libsqlite3-dev
$ sudo apt-get install -y tk-dev
$ sudo apt-get install -y libgdbm-dev
$ sudo apt-get install -y libc6-dev
$ sudo apt-get install -y libbz2-dev
$ sudo apt-get install -y zlib1g-dev
$ sudo apt-get install -y openssl
$ sudo apt-get install -y libffi-dev
$ sudo apt-get install -y python3-dev
$ sudo apt-get install -y python3-setuptools
$ sudo apt-get install -y wget
```
* wget으로 python3.7을 직접 받아서 압축 풀고 사용
```
$ wget https://www.python.org/ftp/python/3.7.0/Python-3.7.0.tar.xz
$ tar xvf Python-3.7.0.tar.xz
$ cd Python-3.7.0
$ ./configure
$ sudo make altinstall
```
* 잘 설치 되었는지 확인
```
$ python3.7 --version
```
* 여기서 이대로 그냥 파이썬을 해본다면 2.7버전이 뜰 것이기 때문에 지금 깔아준 3.7을 공통으로 사용할 수 있도록 만들어준다.
* 기본 베이즈 파이썬 위치를 3.7 깐 곳으로 변경해주면 됨!
* Alternatives 활용
```
# 파이썬3.7 위치
$ which python3.7
/usr/local/bin/python3.7

# (기존에 깔려있는게 있었다면) 파이썬 기본 위치
$ which python
```
* alternatives를 통한 python 경로 변경
```
# alternatives에 등록된 파이썬들 확인 
$ sudo update-alternatives --config python

# alternatvies에 등록
$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.7 1
                                    (파이썬 기본 위치)        (파이썬3.7위치)     (여기 숫자는 나는 아무것도 없었기 때문에 1)
# 등록된 파이썬들을 통해 나중에 바꾸기 가능
$ sudo update-alternatives --config python

# 마지막으로 기본파이썬 버전이 바뀌었나 확인
$ python --version
Python 3.7.0 
```
### :point_right: Cmake 설치
```
$ pip3 install cmake
```

정리끝!!!! Khaiii는 카카오 깃헙에 잘 정리되어 있으니 나중에 거길 보자~  미래의 나에게 :heart:
