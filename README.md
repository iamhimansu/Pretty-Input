# Pretty-Input-Field
Simple use of javascript and css to create a dynamic input field

Attach these simple css and javascript code to your html file and create a dynamic input field.
<br />
(1) Attach <kbd>jquery.js</kbd> get it from here <code>http://code.jquery.com/</code>
    <br />
    <pre><script
    src="http://code.jquery.com/jquery-3.3.1.min.js"
    integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8="
    crossorigin="anonymous"></script></pre>
    
    
   
 (2) Attach this <kbd>CSS</kbd> style.<br />
 
 <pre>*{
            box-sizing: border-box;
        }
        html, body{
            padding: 0;
            margin: 0;
            font-family: sans-serif;
        }
        .container{
            width: 40%;
            border: 1px solid transparent;
            margin: 0 auto;
            padding: 10px;
        }
        .input{
            padding: 8px;
            margin: 15px 0;
            border: 1px solid #e0e0e0;
            border-radius: 3px;
        }
        .input:focus-within, .input-caption{
            border-color: aqua;
            color: aqua;
        }
        .input > input {
            height: 30px;
            padding: 5px 10px;
            margin: 5px 0;
            width: 100%;
            border: none;
            outline: none;
            font-size: inherit;        
        }
        .input > .input-caption{
            position: absolute;
            padding: 0 5px;
            margin: 10px;
            background-color: #fff;
            transition-property: margin;
            transition-duration: 0.02s;
            color: rgba(0, 0, 0, 0.7);
            border-radius: 3px;
            font-size: inherit;
            max-width: 98%;
        }
        .input > .caption-title{
            margin-top: -1.1rem;
            font-size: 14px;
        }
        .input > input::placeholder{
           visibility: hidden;
        }
        .input:focus-within > input::placeholder{
            visibility: visible;
        }
        </pre>
        
<br />(3) Add class <kbd>input</kbd> to the parent class containing that <kbd>input field</kbd>
<pre>For example:
        < div class="form-control input">
        < span class="input-caption">Enter email address</ span>
        < input type="text" placeholder="Enter your email" />
        < /div>
        </pre><br />
(4) Add this JS SNIPPET to your HTML file.

```javascript
    $(".input").on("focusin",function(i){$(this).children(".input-caption").addClass("caption-  title")}),$(".input").on("click",function(i){$(this).children(".input-caption").addClass("caption-title"),$(this).children("input").focus()}),$(".input").on("focusout",function(i){var t=$(this).children("input").val();0<$.trim(t).length?$(this).children(".input-caption").addClass("caption-title"):$(this).children(".input-caption").removeClass("caption-title")});
```
<br />
# Hey! you created your dynamic input field
<br />
<pre>Changes : If your are using bootstrap copy this css into your style</pre><br />
<pre>.form-control:focus{
            border: none;
            outline: none;
            box-shadow: none;
        }
        </pre>
<br /><b>This removes the default ouline shadow of input fields</b>
