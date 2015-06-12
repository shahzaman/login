<?php
include('Login.php'); // include login scripit
?>
<!doctype html>
<html>
<head>
    <title>Log in</title>
    <link href="style.css" rel="stylesheet">
 
</head>
<body>


<div class="header">
     <div class="header_bar">
        <img src="images/logo.jpg" width="150" height="100">
        
</div>
</div>
    

<section data-role="content">

 <div class="content">

 <hgroup class="title"><h1>Log in.</h1></hgroup>
 <form action="login.php" novalidate method="post">
 <div class="content_noborder">
 <div class="reg_box">
   <div class="head_bar2"> Not yet registered? </div>
   <div class="content_reg">
   "
                You must be registered to place an ad.
           "
           <br>
           <br>
           <br>
           "

                If you are not registered yet , "
                <a class="abutton" href="Register.html">Click here</a>
                <br>
                "
                Registration is "
                <b>free of charge and without obligation.</b>
                <br>
                <br>
                "

                If you are registered, enter your ID and password on the right-hand side of this page."
            
           </div>     
   </div>
     <div class="reg_box">
     <div class="head_bar2">Already registered?</div>
     <div class="content_reg">
     <div class="reg_bar">
                    <b>To access your account, enter your user name and password and then click on Confirm :</b>
                </div>

                <div class="reg_bar">
                    <div class="reg_smallbar_left" style="margin-top: 5px">
                        User name :
                    </div>
                    <div class="reg_smallbar_right">
                        <input class="txt_box" data-val="true" data-val-required="The User name field is required." id="UserName" name="username" required type="text" value="" />
                        <span class="field-validation-valid" data-valmsg-for="UserName" data-valmsg-replace="true"></span>
                    </div>
                </div>

                <div class="reg_bar">
                    <div class="reg_smallbar_left" style="margin-top: 5px">
                        Password :
                    </div>
                    <div class="reg_smallbar_right">
                        <input class="txt_box" data-val="true" data-val-required="The Password field is required." id="Password" name="pass_word" type="password" />
                        <span class="field-validation-valid" data-valmsg-for="Password" data-valmsg-replace="true"></span>
                    </div>
                </div>

                <div class="reg_bar">
                    <div class="reg_smallbar_left">
                    </div>
                    <div class="reg_smallbar_right">
                        <input type="submit"  name="submit" value="Login" class="btn_dark" />
                    </div>
                </div>
                <div class="reg_bar">
                    <span class="field-validation-valid" data-valmsg-for="Login" data-valmsg-replace="true" style="width:100%"></span>
                </div>


               
                
            </div>
        
        </div>

 </div>
    </form>
</div>

</section>

<!-- End DWUser_EasyRotator -->
<section data-role="footer" class="footer">
            <footer>
                <div class="footer">
                
                </div>
            </footer>
        </section>
</body>
</html>
