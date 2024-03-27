# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>
<body>
    <style>
        .icon {
            color: red;
            font-size: 25px;
            padding: 1%;
        }
        .icon:hover {
            color: gray;
        }
        a {
            padding: 10px;
            font-family: 'Courier New';
            color: darkcyan;
            text-decoration: dotted;
            font-size: 20px;
        }

        a:hover {
            color: red;
        }
    </style>
    <div style="height: 100%; background-color: #dcdcdc;">
        <div class="row border border-3" style="background-color: #dcdcdc; height:10%">
            <div class="col-5">
                <i class="bi bi-twitter icon"></i>
                <i class="bi bi-youtube icon"></i>
                <i class="bi bi-facebook icon"></i>
                <i class="bi bi-linkdin icon"></i>
                <i class="bi bi-whatsapp icon"></i>
                <i class="bi bi-instagram icon"></i>
            </div>
            <div class="col-4">
                <nav class="navbar navbar-expand-lg">
                    <div class="container-fluid">
                        <div class="collapse navbar-collapse" id="navbarSupportedContent">
                            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                                <li class="nav-item">
                                    <a class="nav-link active" aria-current="page" href="#">Alumini</a>
                                </li>
                                <li class="nav-item">
                                    <a class="nav-link" href="#">Events</a>
                                </li>
                                <li class="nav-item dropdown">
                                    <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown"
                                        aria-expanded="false">
                                        Department
                                    </a>
                                    <ul class="dropdown-menu">
                                        <li><a class="dropdown-item" href="#">CSE</a></li>
                                        <li><a class="dropdown-item" href="#">IT</a></li>
                                        <li>
                                            <hr class="dropdown-divider">
                                        </li>
                                        <li><a class="dropdown-item" href="#">ECE</a></li>
                                        <li><a class="dropdown-item" href="#">EEE</a></li>
                                    </ul>
                                </li>
                            </ul>
                        </div>
                    </div>
                </nav>
            </div>
            <div class="col-2">
                <input type="search" placeholder="search" style="border-radius:3px; padding:3px;">
            </div>
        </div>
        <div style="display: flex; height:20%;background-color: white" >
            <div style="width: 40%; padding-top :3%">
                <img style="width: 100%;"
                    src="https://th.bing.com/th/id/R.034cf1cf14661ed9a95b8de0ac808853?rik=A0VCwkWaTLYFWg&riu=http%3a%2f%2ftraining.saveetha.in%2fpluginfile.php%2f1%2fcore_admin%2flogo%2f0x200%2f1623542614%2flogo_1.png&ehk=xh37cRaMdzwXDSnajURQi%2fR8HDRqlqr5i7O9o3ZdCQc%3d&risl=&pid=ImgRaw&r=0"
                    alt="">
            </div>
            <div style="width: 55%; padding:5%; padding-left: 1%; ">
                <a href="">Home</a>
                <a href="">DEPT</a>
                <a href="">Life at SEC</a>
                <a href="">Placement</a>
                <a href="">About</a>
            </div>
            <div style="width: 20%; padding-top: 4%;">
                <input style="height: 30px;
                width: 80%;
                background-image : url(html/search-removebg-preview.png);
                background-size: contain;
                background-repeat : no-repeat;
                border-radius : 15px;
                padding-left : 40px; " type="text" name="search">
    
            </div>
        </div>

        <div style="display:flex; height:30%;">
            <div style="width: 30%;" style="color: red;"></div>
            <div style="width: 70%; padding-top:1%; padding-right:1%">
                <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
                    <div class="carousel-indicators">
                        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0"
                            class="active" aria-current="true" aria-label="Slide 1"></button>
                        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1"
                            aria-label="Slide 2"></button>
                        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2"
                            aria-label="Slide 3"></button>
                        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="3"
                            aria-label="Slide 4"></button>
                        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="4"
                            aria-label="Slide 5"></button>
                    </div>
                    <div class="carousel-inner">
                        <div class="carousel-item active">
                            <img src="https://motionbgs.com/media/1407/luffy-gear.jpg" class="d-block w-100" alt="...">
                        </div>
                        <div class="carousel-item">
                            <img src="https://th.bing.com/th/id/OIP.-TaoV93kMxYIJQ4QcnEJKQHaEK?rs=1&pid=ImgDetMain"
                                class="d-block w-100" alt="...">
                        </div>
                        <div class="carousel-item">
                            <img src="https://th.bing.com/th/id/OIP.7Mmam9FLO4KzFBOqkPc1cwHaEK?rs=1&pid=ImgDetMain"
                                class="d-block w-100" alt="...">
                        </div>
                        <div class="carousel-item">
                            <img src="https://th.bing.com/th/id/OIP.8-ZuLQgklT8RiOdLb2rg3AHaEK?rs=1&pid=ImgDetMain"
                                class="d-block w-100" alt="...">
                        </div>
                        <div class="carousel-item">
                            <img src="https://th.bing.com/th/id/OIP.ApWLnkO6TBa7e6U6AKjwEwHaEK?rs=1&pid=ImgDetMain"
                                class="d-block w-100" alt="...">
                        </div>
                    </div>
                    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators"
                        data-bs-slide="prev">
                        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                        <span class="visually-hidden">Previous</span>
                    </button>
                    <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators"
                        data-bs-slide="next">
                        <span class="carousel-control-next-icon" aria-hidden="true"></span>
                        <span class="visually-hidden">Next</span>
                    </button>
                </div>
            </div>
        </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
        crossorigin="anonymous"></script>
</body>
</html>

## OUTPUT:
<img width="905" alt="capture1" src="https://github.com/NaveenKumarV2005/simplewebserver/assets/151476286/c373aa47-e6f4-4837-996a-0d07a6e16aa4">
![Uploading capture2.png…]()


## RESULT:
The program for implementing simple webserver is executed successfully.
