## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/NitinMohanty1/Tambola/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block
<!DOCTYPE html>
        <html>
            <head>
                <meta charset=utf-8 />
                <title>Housie Ticket Generator</title>
                <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.3.2/jquery.min.js"></script>
                <script type="text/javascript" src="assets/js/script.js"></script>
                <link rel="stylesheet" type="text/css" media="screen" href="assets/css/style.css"/>
            </head>
            <body style="background-image: url(https://media.istockphoto.com/vectors/space-background-with-realistic-nebula-and-shining-stars-colorful-vector-id1173451503?k=20&m=1173451503&s=612x612&w=0&h=nyxt3C6OjEFcquvjLALrIz-67IEOEpfKNBvR8qi4sLA=);background-repeat:no-repeat; background-size:cover">
                <h1 style="font-family:Stencil" align="left">Tambola Ticket</h1><h2 style="color: White; font-family:Stencil">Timestamp: <span style="color:white; font-family:Stencil" id="txt"></span></h2>
                <body onload="startTime()"></body>
            <img src="https://drive.google.com/uc?export=view&id=1rxRE4EMXazAV3FwStQ-Bh07d9KQT-2lN">
         
            <br><table id="table2" class= "innerTable">
                        <tbody id="tbodyid">
                        <tr>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                        </tr>
                        <tr>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                        </tr>
                        <tr>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                            <td><input size=1px type='text'/></td>
                        </tr>
               </table>
               </div>
               </td>
               </tr>
               </table>
               
<style type="text/css">
               #page{
        width:455px;
        margin:0 auto;
    }

.innerTable{
    table-layout: fixed;
    width:50px;
}

    td{
        font-family:Verdana;
        table-layout: fixed;
        color:#333;
        padding:4px;
        width:45px;
        height:45px;
        font-weight:bolder;
        text-align:center;
        border:5px solid #ddad75;
        background-color:#eee;
    }

   
    h1, h4 a{
        font-family:arial;
        text-align:center;
        padding:3px;
        color:#211111;
        background-color:#EEEEEE;
        border:2px solid #DDDDCC;
    }

    td{
        cursor:pointer;
    }
</style>    
<script type="text/javascript">
    $(document).ready(function(){
               
        var count =0;
        var baseArrayNew = new Array(0,9,19,29,39,49,59,69,79,90);
        var baseArrayStart = new Array(0,1,10,20,30,40,50,60,70,80);
        var number = 0;               
        var base = 0;
        var selectRow=0 ;
        var j =0 ;
        var newNo=0;
        var countArray =0;
        var arrNew = [];  
        var arr = []
        var aryKeyValue = [];
        var arrKeyValuePair=[];
                
        publish();
               
        function init(){
            arrKeyValuePair=[];
            aryKeyValue = [];
         arrKeyValuePair=[];
             arr = [];
             arrNew = []; 
             count =0;
             number = 0; 
             base = 0; 
             selectRow=0 ;  
             j =0 ;
             newNo=0;
             countArray =0;

                    arr=    getRandomColumn();
                     arr.sort(function(a, b){return a-b});
                  for(var i = 0; i<arr.length; i++){
                   
                    var num=getRandomNum(arr[i]);
                    if(checkUniqueNess(num,arrKeyValuePair)==false){
                     while(checkUniqueNess(num,arrKeyValuePair)==false){
                      var num=getRandomNum(arr[i])
                     }
                     //console.log(" true ");  
                    }   
                        pushToAry(arr[i],num);
                        sortArray(arrKeyValuePair,arr[i],num);
                         
                    }
                    return arrKeyValuePair;
                    //publish(arrKeyValuePair);
                   // printArray(arrKeyValuePair);
                }
           // get random columns 	
        function getRandomColumn(){

                while(arr.length <15){
                      var randomnumber=Math.ceil(Math.random()*9)
                      var found=false;
                      if(count>=5 && count<10){
                            randomnumber=randomnumber+10;
                        }else if(count>=10){
                             randomnumber=randomnumber+20;
                        }
                      for(var i=0;i<arr.length;i++){
                        
                        if(arr[i]==randomnumber){
                          found=true;
                          break;
                        }
                      }
                      if(!found){
                        arr[arr.length]=randomnumber;
                        count++;
                    }
                    }
               return arr;
             }
             //get random nuumber for respective column
        function getRandomNum(i){
          var start =0;
                    if(i>10){
                            // convert number to a string, then extract the first digit
                    var one = String(i).charAt(1);
                    // convert the first digit back to an integer
                    newNo =Number(one); 
                     j =newNo ;  
                           }
                    else{
                        j = i ;
                        }
                     base = (baseArrayNew[j]);
                     start =  baseArrayStart[j];
                    //return Math.floor(Math.random() * (max - min + 1)) + min;
                    
                    number = Math.floor(Math.random() * (base-start + 1)) + start;
                    
                   //number = base + Math.floor(Math.random()*9)+1;
                    return   number;      
                        }
        //check for uniqueness                
        function checkUniqueNess(number,arrNew){
             var res =0 ;
              var value=0;
                   var found =false;

                    for(var i=0;i<arrNew.length;i++){
                         res = arrNew[i].split(":");
                          value=res[1];
                        if(value==number){
                          found=true;
                          return false;
                          break;
                          
                        }
                      }
                       if(!found){
                       // arrNew[arrNew.length]=number;
                        return true;
                       
                    }
                            
        }
        //sort the array
        function sortArray(arr,keySort,num){
               var res =0 ;
               var key =[];
               var value=[];
                var arySort = [];
                var sort = false;
                 value[value.length]=num;  
               for(var i=0;i<arr.length;i++){
                 
                res = arr[i].split(":");
                  //console.log("RES : "+ res);
                 key=res[0];
                 if(keySort+10==key || keySort+20==key ||keySort-10==key || keySort-20==key){
                 //console.log("key : "+ key);
                  value[value.length]=res[1];  
                  sort = true; 
               }
           }
              
               if (sort){
                 value.sort(function(a, b){return a-b});
                 arrangeSort(arr,key, value)
               }
            
             }
// arrange the array
        function arrangeSort(arr, keyOld,val) {
              var str ;
              var j=0 ;
               for(var i=0;i<arr.length;i++){
                 
                res = arr[i].split(":");
               //  console.log("RES : "+ res);
                 key=res[0];
                 if(keyOld+10==key || keyOld+20==key ||keyOld== key||keyOld-10==key || keyOld-20==key){
                //console.log("key : "+ key);
                   str = key+":"+val[j] ;
                  //  console.log("str : "+ str);
                  arr[i]=str;
                  j++;
               }
            }
            } 
// add to arr random no. with random columns
        function pushToAry(name, val) {
            arrKeyValuePair.push(name+":"+val);
             return  arrKeyValuePair;
              
            }
        function publish() {
        var res =0 ;
        var value=0;
        var key =0;
        var rownum=0;
        var aryKeyValue =[];
        for(var j =1;j<=12;j++){
        aryKeyValue=  init();
        var table = document.getElementById("table"+j);
            for(var i=0;i<aryKeyValue.length;i++){
                res = aryKeyValue[i].split(":");
                key=res[0];
                value=res[1];
               // console.log("KEY "+key);
                if(key>10){

              rownum= ~~(key/10);
                }else{
                    rownum=0;
                }
                // console.log("rownum: "+rownum);
                 table.rows[rownum].cells["cell"+key].innerHTML=value;
            }
        }
         }
// clear all colums
    function clear() {
        
        for(var j =1;j<=12;j++){
        var table = document.getElementById("table"+j);
        for(var row =0 ;row<=2;row++){
            for(var i=1+(row*10);i<=9+(row*10);i++){
                if (i==10||i==20){

                }else{
                     table.rows[row].cells["cell"+i].innerHTML="";
                }
                
            }
        }
        }
         }
// print command to check
        function printArray(aryKeyValue) {
              
            for(var i=0;i<aryKeyValue.length;i++){
            console.log( aryKeyValue[i]);
            }
            }
           
    function printDiv() {
            var toPrint = document.getElementById('printarea');
            var popupWin = window.open('', '_blank', 'width=350,height=150,location=no,left=200px');
            popupWin.document.open();
            popupWin.document.write('<html><title>::Preview::</title><link rel="stylesheet" type="text/css" href="assets/css/style.css" /></head><body onload="window.print()">')
            popupWin.document.write(toPrint.innerHTML);
            popupWin.document.write('</html>');
            popupWin.document.close();
    }

            	 
                $('#newCard').click(function(){
                    clear();
                    publish();
                });

                $('#printBut').click(function(){
                   printDiv()
                });
            	 
        
            });

function startTime() {
  const today = new Date();
  let h = today.getHours();
  let m = today.getMinutes();
  let s = today.getSeconds();
  m = checkTime(m);
  s = checkTime(s);
  document.getElementById('txt').innerHTML =  h + ":" + m + ":" + s;
  setTimeout(startTime, 1000);
}

function checkTime(i) {
  if (i < 10) {i = "0" + i};  // add zero in front of numbers < 10
  return i;
}
            </script>
            </body>
        </html>
# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/NitinMohanty1/Tambola/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we???ll help you sort it out.
