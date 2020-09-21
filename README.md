# django_user
1. Buat Repository di github
2. Copy url & paste url github di pycharm
3. Setup VENV di menu setting pycharm
4. Install Django di menu setting pycharm
5. Jalankan perintah di bawah ini pada terminal :
   mkdir mysite
6. Jalankan perintah di bawah ini pada terminal :
   cd mysite
7. Jalankan perintah di bawah ini pada terminal :
   django-admin.py startproject mysite .
8. Jalankan perintah di bawah ini pada terminal :
   python manage.py runserver
9. Jalankan perintah di bawah ini pada terminal :
   python manage.py migrate
10. Jalankan perintah di bawah ini pada terminal :
    python manage.py createsuperuser
11. Isikan data username, email dan password
12. Ketikkan url ini : http://127.0.0.1:8000/admin
13. Login username & password yang sebelumnya sudah didaftarkan 
14. Jalankan perintah di bawah ini pada terminal :
    python manage.py startapp authenticate
15. Tambahkan authenticate pada setting.py yang ada di dalam folder mysite
    INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'authenticate',
        ]   
16. Copy file urls pada folder mysite & paste file urls pada folder authenticate
17. Update isi file urls pada folder authenticate dengan kode sbb: 
    from django.urls import path
    urlpatterns = [
    ]
18. Update isi file urls pada folder mysite dengan kode sbb:
    from django.contrib import admin
    from django.urls import path,include
    urlpatterns = [
        path('admin/', admin.site.urls),
        path('',include('authenticate.urls'))
    ]
19. Tambahkan library di bawah library from django.urls import path :
    from . import views
20. Buat folder baru bernama templates di dalam folder authenticate
21. Buat folder baru bernama authenticate di dalam folder templates
22. Buat file html baru bernama home.html di dalam folder authenticate
23. Tambahkan kode di bawah ini pada file views di bawah library from django.shortcuts import render di dalam folder authenticate:
    def home(request):
    return render(request,'authenticate/home.html',{})
24. Tambahkan kode di bawah ini pada file urls di bawah from . import views di dalam folder authenticate:
    urlpatterns = [
    path('',views.home,name="home")
    ]
25. Tambahkan kode html di bawah ini pada file home.html di bawah tag body di dalam folder authenticate:
    <h1>Home Page</h1>
    <p>Ini adalah halaman Home</p>
26. Buat file baru base.html di dalam folder authenticate
27. Copy starter template bootstrap4 di website https://getbootstrap.com/docs/4.5/getting-started/introduction/
28. Paste starter template booststrap4 di file base.html
29. Tambahkan kode di bawah ini di dalam tag body pada file base.html :
    {% block content %}
    {% endblock %}
30. Update kode html di bawah ini di dalam file home.html di dalam folder authenticate:
    {%extends 'authenticate/base.html'%}
    {%block content%}
    <h1>Home Page</h1>
    <p>Ini adalah halaman Home</p>
    {%endblock%}
31. Tambahkan kode di bawah ini di dalam file base.html di dalam folder authenticate:
    <div class="container">
    {%block content%}
    {%endblock%}
    </div>
32. Copy template navbar yang ada di web https://getbootstrap.com/docs/4.5/components/navbar/
33. Paste template navbar tsb di bawah tag body di dalam file base.html
34. Beri Tag comment pada <form class="form-inline my-2 my-lg-0"> </form> pada file base.html
35. Beri Tag comment pada <li class="nav-item"></li> pada file base.html
36. Beri Tag comment pada <li class="nav-item dropdown"></li> pada file base.html
37. Beri Tag comment pada <li class="nav-item active"></li> pada file base.html
38. Beri Tag comment pada <li class="nav-item active"></li> pada file base.html
39. Ubah code html <ul class="navbar-nav mr-auto"> menjadi seperti di bawah ini pada file base.html di dalam folder authenticate
    <ul class="navbar-nav ml-auto">
40. Ubah code html <a class="navbar-brand" href="#">Navbar</a> menjadi seperti di bawah ini pada file base.html di dalam folder authenticate
    <a class="navbar-brand" href="{% url 'home' %}">Authenticate App</a>