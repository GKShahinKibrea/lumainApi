# First class (Laravel Lumen Introduction)
Demand of Api Developer
* one databse Multiple of Software
* Multiple Sofware Connected With Each Other
* On Company Share Data With Another Company

Big Example of Api
* All google Service - YouTube, Gmail, Google Drive, Play Store
* Facebook Service - Facebook, Messenger, Login
* Money Transfer Service - Skrill, Paypal, Payoneer, Bkash
* AI/Machine Learning - Face Recognition, Finger Print, Object Detection

What is Laravel lumen
* Lumen is a laravel micro service
* Lumen is used for building fast and secure rest API
* Lumen can use with web app, mobile app, IOT services, desktop app.
* Lumen uses rate is higher than other micro services in php
* silex use per second 1000 , Slim 3 use per second 1800, Lumen use per second 1900

# Second class (Laravel Lumen Tools)
Tools
1. VS Code
2. PhpStrom
3. Xammp
4. Postman
5. Composer

# Third class (Create And Run New Project)
Installing Lumen
* composer create-project --prefer-dist laravel/lumen blog

Project Run
* php -S localhost:8000 -t public

# Four class (Lumen API File Structure)
File Structure:

* controllers: our app logics.
* middlewares: API Security here.
* migrations: Database schema here.
* model: Data model here.
* routes: Endpoints for the API.
* .env: Database Connection.
* web: Main Routing Point

# Five class (Lumen API Basic Routing)
Methods For Rest API

* $router->get($url,$callback);
* $router->post($url,$callback);
* $router->put($url,$callback);
* $router->delete($url,$callback);
* post, put, delete route only test postman

$router->get('/get', function () use ($router) {
    return "This is get method";
});

$router->post('/post', function () use ($router) {
    return "This is post method";
});

$router->put('/put', function () use ($router) {
    return "This is put method";
});

$router->delete('/delete', function () use ($router) {
    return "This is delete method";
});

$router->post('/kibu',function() {
    return "I am Golam Kibrea";
});

# Six class (Route Prameter)
Route Parameters
* Required Parameters
* Optional Parameters

Required Single Parameters
---------------------------
$router->post('/name/{value}',function($value){
	return $value;
});

postman post test : http://localhost:8000/name/shahinkibrea

Required Multipule Parameters
---------------------------
$router->post('/name/{value}/age/{age}',function($value, $age){
	return $value.' '.$age;
});

postman post test : http://localhost:8000/name/shahinkibrea/age/25

$router->post('/{name}/{age}/{city}',function($name, $age, $city){
	return $name.' '.$age.' '.$city;
});

postman post test : http://localhost:8000/shahinkibrea/32/Tokyo

Optional Parameters
---------------------------

$router->post('/{name}/{age}[/{city}]',function($name, $age, $city=null){
	return $name.' '.$age.' '.$city;
});

postman post test : http://localhost:8000/shahinkibrea/32

# Class Seven (What is Rest API & History)

* Roy Fielding defined REST in his 2000 phD
 (Representational State Transfer)

 ## What is Rest Api(Representational State Transfer)

 Client Script <----------  API Script <----------- Database
* Client-server 
* Stateless
* Cacheable
* Uniform interface

# Class Eight (Laravel Lumen API Controller)

* What is controller?
Controller is a class to organize the logics of http request.Controller gather data from 
model class and prepare it for request.

* How to create controller?
We can create a controller class by extends it to Controller class in laravel lumen. <br />
Example Code :  <br />

  <?php  <br />

  namespace App\Http\Controllers;  <br />
  use App\User;  <br />

  class MyController extends Controller {  <br />
    
  }  <br />

* How to use controller?
We use controller class as callback function in route like 'ControllerClass@Method'  <br />
How Pass Parameter To Controller?  <br />
$router->get('/{id}','MyCon@My')  <br />

# Class Nine (Laravel Lumen API Controller)
* Controller code :  <br />
namespace App\Http\Controllers; <br />
use App\User; <br />

class MyController extends Controller { <br />
    public function My(){ 
        return "This is my Router"; 
    } 

    public function Myparameter($name){ 
        return "This is my parameter ".$name; 
    } 
} <br />

* Route code : 
$router->get('/','MyController@My');  <br/>
$router->get('/{name}','MyController@Myparameter');  <br/>

# Class TEN (API Response)

Response Area :
* Body
* Header

Response Type
* Simple String 
* JSON
* XML
* Download
* Redirect

Details of API Response
* Simple String Response Header And Body
* Json Response Body From various Types Of Array
* Redirect Response To Another URI
* UnderStanding Download Response

# Class Eleven (Simple String Response Header And Body)

* only use String Response Body </n>
 return response($content)
* Both Use String Response Body and Header  </n>
 return response($content)  </n>
        ->header('Content-Typle',$type)  </n>
        ->header('X-Header-One','Header Value');
* Test Code : </n>
    public function Myparameter($name){
        return response($name)
                ->header('age','28')
                ->header('city','Tokyo')
                ->header('admin','user'); }

# Class TWELVE JSON Response in Body From Array
* return response()->json('name'=>'shahinkibrea','age'=>'23'); <br/>
* only show Body . Dont Show Header.

Example code : 

 public function My(){
        $myArray = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
        return response()->json($myArray);
    }

 $router->get('/','MyController@My');

# Class Thirteen (Response Redirect And Download)
* Response Redirect 
return redirect()->route('login');

Code Example :
    public function First(){
        return redirect('/Second');
    }

    public function Second(){
        return "This is Second Method.";

    }

$router->get('/First','MyController@First');
$router->get('/Second','MyController@Second');

* Response Download
return response()->download($pathToFile);
 create file public Folder/ demo.txt

Code Example :

public function Download(){
        $path = 'Demo.txt';
        return response()->download($path);
}

$router->get('/Download','MyController@Download');

# Class Fourteen Sending And Catching Request Data

Sending And Catching

Way of Send And Catch:
* Via URL Parameter
* Via Header
* JSON Data Via Body

Send(Mobile/other Device)------------> Catch,Slice (Api)----------> Database

# Class Fiften Sending And Catching Request Data

Sending And Catching

Way of Send And Catch:
* Via URL Parameter -> postman parameter pass key : value 
* Via Header -> postman Header pass key : value 
* JSON Data Via Body -. postman Body pass key : value 

Send(Mobile/other Application)------------> Catch,Slice (Api)----------> Database

Example:
<?php
namespace App\Http\Controllers;
use App\User;
use Illuminate\Http\Request;

class MyController extends Controller {
    
    public function Catch(Request $request){
        when use parameter and Body
        return $request();

        when use Hader
        return $request()->header('name');
    }
}

* $router->get('/Catch','MyController@Catch'); </n>

# Class 19 (Create New DB And Connect)

## Database Operation 
1. Database Connection
2. Select, Insert, Update, Delete
3. Database Migration

* Create Database
1. DB Name : details
2. Table Name : details
   1. id->primaryKey,AutoIncreament
   2. name,roll,city,phn,class->varchar(50)
   3. Demo Data Insert

.env : 
     DB_CONNECTION=mysql
	 DB_HOST=127.0.0.1
	 DB_PORT=3306
	 DB_DATABASE=students
	 DB_USERNAME=root
	 DB_PASSWORD=
