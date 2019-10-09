
# Django guide 

### 1. 가상환경 생성 및 실행  

 - 가상환경 생성
   ```python
   python -m venv myvenv  
   # python -m venv 가상환경이름  
   ```
       
 - 가상환경 실행 및 종료
   ```python
   Source myvenv/Scripts/activate  # 가상환경 실행  
   deactivate  # 가상환경 종료 
   ```

### 2. Dajgno install 
 - 설치 및 삭제  
   ```python
   pip install dajngo #  장고 설치
   pip uninstall django #  장고 삭제  
   ```

### 3. Dajngo 프로젝트 생성
 - 프로젝트 만들기  
   ```python
   django-admin startproject <projectname>  
   ```
 - 서버 실행  
   ```python
   python manage.py runserver  
   ```
 - 앱 만들기  
   ```python  
   python manage.py startapp <appname>  
   ```
 - 앱 등록하기  
 django 앱을 사용하기 위해 settings.py INSTALLD_APPS 영역에 생성한 앱을 등록한다.  
   ```python
   INSTALLED_APPS = [ 
          'myapp.apps.MyappConfig',
   ]  
   ```
 - views.py 작성  
 예로 home이라는 함수를 정의. 요청이 왔을 때 home.html을 리턴한다. (MBV, CBV 등)
   ```python
   def home(request) :
       return render(request,'home.html')  
   ```
 - url path 설정  
   ```python
   import myapp.views  # view에 있는 home 메소드와 url을 연결하기 위해
   urlaptterns = [
         path('',myapp.views.home,name="home"),
         # ''와 같은 url 요청이 발생할 경우 myapp.views에 home 메소드를 호출
   ]  
   ```
 
 ### 3. Migrations delete  
 - cmmand
   ```python
   find . -path "*/migrations/*.py" -not -name "__init__.py" -delete
   find . -path "*/migrations/*.pyc" -delete
   ```

   
   
