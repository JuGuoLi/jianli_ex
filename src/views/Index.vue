<template>
    <div>
        <div id='touxiang'>
            <div>
                <div>
                    <p>{{this.touxiang_data.title1}}</p>
                    <p>{{this.touxiang_data.title2}}</p>
                    <p>{{this.touxiang_data.title3}}</p>
                    <p>{{this.touxiang_data.title4}}</p>
                </div>
                <a href="#about_me">
                    <div id='click_button'>
                        <p></p>
                    </div>
                </a>
            </div>
        </div>
        <div id='about_me'>
            <div>
                <h3>自身介绍</h3>
                <div>
                    <div>
                        <img src="../assets/computer.jpg" alt="">
                        <h4>PC端开发</h4>
                    </div>
                    <div>
                        <img src="../assets/phone.jpg" alt="">
                        <h4>移动端开发</h4>
                    </div>
                    <div>
                        <img src="../assets/people.jpg" alt="">
                        <h4>团队成员</h4>
                    </div>
                    <div>
                        <img src="../assets/gezi.jpg" alt="">
                        <h4>整体流程</h4>
                    </div>
                    <div>
                        <img src="../assets/notes.jpg" alt="">
                        <h4>所遇困难</h4>
                    </div>
                </div>
                <div id='about_bottom'>
                    <div>
                        <h4>
                        {{about_me_data.title1}}
                        </h4>
                    </div>
                    <div>
                        <p>
                        {{about_me_data.title2}}
                        </p>    
                    </div>
                    <div>
                        <p>
                        {{about_me_data.title3}}
                        </p>
                    </div>
                </div>
            </div>
        </div>
        <div id='demo'>
            <div>
                <h3>个人项目</h3>
                <ul>
                    <li><a href="javascript:;" :class='`${demo_a==1?"demo_font_active":""}`' @click='demo'>所有</a></li>
                    <li><a href="javascript:;" @click='demo_1' :class='`${demo_b==1?"demo_font_active":""}`'>前端项目</a></li>
                    <li><a href="javascript:;" @click='demo_2' :class='`${demo_c==1?"demo_font_active":""}`'>移动端项目</a></li>
                </ul>
                <div id='demo_bottom'>
                    <ul>
                        <li v-for='item of demo_data' :key='item.id'>
                            <img :src="item.pic" alt="" @click='open'>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        <div id='bg_img'>
            <ul>
                <li>
                    <h2>PC端项目</h2>
                    <p>54</p>
                </li>
                <li>
                    <h2>移动端项目</h2>
                    <p>39</p>
                </li>
                <li>
                    <h2>奖项</h2>
                    <p>21</p>
                </li>
            </ul>
        </div>
        <div id='jiaoyu'>
            <div>
                <h3>教育背景和项目经验</h3>
                <h4>教育背景</h4>
                <div v-for="item of jiaoyu_data" :key='item.id'>
                    <div>
                        <span>{{item.data}}</span>
                        <p>{{item.title1}}</p>
                    </div>
                    <div>
                        <h3>{{item.title2}}</h3>
                        <h4>{{item.title3}}</h4>
                    </div>
                </div>
                <h4>项目经验</h4>
                <div id='work'>
                    <div class='work' v-for='item of project_data' :key='item.id'>
                        <div>
                            <p>{{item.title1}}</p>
                            <h3>{{item.title2}}</h3>
                        </div>
                        <div>
                            <h3>{{item.title3}}</h3>
                            <p>{{item.title4}}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div id='bg_data'>
            <ul>
                <li>
                    <canvas id="c1" width='200px' height='200px'></canvas>
                    <h4>html、css</h4>
                </li>
                <li>
                    <canvas id="c2" width='200px' height='200px'></canvas>
                    <h4>nodejs、MySQL等</h4>
                </li>
            </ul>
            <ul>
                <li>
                    <canvas id="c3" width='200px' height='200px'></canvas>
                    <h4>vue|angular|react</h4>
                </li>
                <li>
                    <canvas id="c4" width='200px' height='200px'></canvas>
                    <h4>javascript</h4>
                </li>
            </ul>       
        </div>
        <div id='contact_me'>
            <div>
                <h2>
                    联系我
                </h2>
                <div>
                    <h2>地址</h2>
                    <p>{{contact_me_data.title1}}</p>
                </div>
                <div>
                    <h2>邮箱</h2>
                    <p>{{contact_me_data.title2}}</p>
                    <p>{{contact_me_data.title3}}</p>
                </div>
                <div>
                    <h2>电话</h2>
                    <p>{{contact_me_data.title4}}</p>
                    <p>{{contact_me_data.title5}}</p>
                </div>
            </div>
        </div>
        <div id='thanks'>
            <p>{{thanks_data.title1}}</p>
        </div>
        <div id='demo_content_1' :class='`${close_data==1?"hide":""}`'>
                        <h1>项目</h1>
                        <img :src="demo_content_data.pic" alt="">
                        <h3>{{demo_content_data.title}}</h3>
                        <button @click='close' >关闭</button>
                    </div>
    </div>
    
</template>

<script>
    export default {
        data(){
            return{
                touxiang_data:[],
                about_me_data:[],
                demo_data:[],
                jiaoyu_data:[],
                project_data:[],
                contact_me_data:[],
                thanks_data:[],
                jianli_index_img_data:[],
                demo_content_data:[],
                demo_a:1,
                demo_b:0,
                demo_c:0,
                close_data:1
            }
        },
        created(){
            this.touxiang();
            this.about_me();
            this.demo();
            this.jiaoyu();
            this.project();
            this.contact_me();
            this.thanks();
            this.demo_content();
        },
        mounted(){
            this.canvas_1();
            this.canvas_2();
            this.canvas_3();
            this.canvas_4();
        },  
        methods:{
            touxiang(){
                var url='http://127.0.0.1:3002/touxiang'
                this.axios.get(url).then(res=>{
                    this.touxiang_data=res.data[0];
                })
            },
            about_me(){
                var url='http://127.0.0.1:3002/about_me';
                this.axios.get(url).then(res=>{
                    this.about_me_data=res.data[0];
                })
            },
            demo(){
                var url='http://127.0.0.1:3002/demo';
                this.axios.get(url).then(res=>{
                    this.demo_data=res.data;
                    this.demo_b=0;
                    this.demo_c=0;
                    this.demo_a=1;

                })
            },
            demo_1(){
                var url='http://127.0.0.1:3002/demo_1';
                this.axios.get(url,{params:{title:'web'}}).then(res=>{
                    this.demo_data=res.data;
                    this.demo_a=0;
                    this.demo_c=0;
                    this.demo_b=1;
                })
            },
            demo_2(){
                var url='http://127.0.0.1:3002/demo_1';
                this.axios.get(url,{params:{title:'phone'}}).then(res=>{
                    this.demo_data=res.data;
                    this.demo_a=0;
                    this.demo_b=0;
                    this.demo_c=1
                })
            },
            jiaoyu(){
                var url='http://127.0.0.1:3002/jiaoyu';
                this.axios.get(url).then(res=>{
                    this.jiaoyu_data=res.data;
                })
            },
            project(){
                var url='http://127.0.0.1:3002/project';
                this.axios.get(url).then(res=>{
                    this.project_data=res.data;
                })
            },
            thanks(){
                var url='http://127.0.0.1:3002/thanks';
                this.axios.get(url).then(res=>{
                    this.thanks_data=res.data[0];
                })
            },
            contact_me(){
                var url='http://127.0.0.1:3002/contact_me';
                this.axios.get(url).then(res=>{
                    this.contact_me_data=res.data[0];
                })
            },
            demo_content(){
                var url='http://127.0.0.1:3002/demo_content';
                this.axios.get(url).then(res=>{
                    this.demo_content_data=res.data[0];
                    console.log(this.demo_content_data)
                })
            },
            open(){
                this.close_data=0;
            },
            close(){
                this.close_data=1;
            },
            canvas_1(){
                var c1=document.getElementById('c1');
                 var ctx=c1.getContext('2d')
                 ctx.beginPath();
                 ctx.arc(100,100,90,0,2*Math.PI);
                 ctx.strokeStyle='white';
                 ctx.lineWidth=15;
                 ctx.stroke();

                 ctx.beginPath();
                 ctx.arc(100,100,90,-90*Math.PI/180,144*Math.PI/180);
                 ctx.strokeStyle='yellow';
                 ctx.lineWidth=15;
                 ctx.stroke();
                
                var str='65%'
                ctx.font='50px SimHei';
                ctx.fillStyle='black';
                ctx.textBaseline='middle';
                var width=ctx.measureText(str).width
                ctx.fillText(str,100-width/2,100)
            },
            canvas_2(){
                var c2=document.getElementById('c2');
                 var ctx=c2.getContext('2d')
                 ctx.beginPath();
                 ctx.arc(100,100,90,0,2*Math.PI);
                 ctx.strokeStyle='white';
                 ctx.lineWidth=15;
                 ctx.stroke();

                 ctx.beginPath();
                 ctx.arc(100,100,90,-90*Math.PI/180,126*Math.PI/180);
                 ctx.strokeStyle='red';
                 ctx.lineWidth=15;
                 ctx.stroke();
                
                var str='60%'
                ctx.font='50px SimHei';
                ctx.fillStyle='black';
                ctx.textBaseline='middle';
                var width=ctx.measureText(str).width
                ctx.fillText(str,100-width/2,100)
            },
            canvas_3(){
                var c3=document.getElementById('c3');
                 var ctx=c3.getContext('2d')
                 ctx.beginPath();
                 ctx.arc(100,100,90,0,2*Math.PI);
                 ctx.strokeStyle='white';
                 ctx.lineWidth=15;
                 ctx.stroke();

                 ctx.beginPath();
                 ctx.arc(100,100,90,-90*Math.PI/180,180*Math.PI/180);
                 ctx.strokeStyle='purple';
                 ctx.lineWidth=15;
                 ctx.stroke();
                
                var str='75%'
                ctx.font='50px SimHei';
                ctx.fillStyle='black';
                ctx.textBaseline='middle';
                var width=ctx.measureText(str).width
                ctx.fillText(str,100-width/2,100)
            },
            canvas_4(){
                var c4=document.getElementById('c4');
                 var ctx=c4.getContext('2d')
                 ctx.beginPath();
                 ctx.arc(100,100,90,0,2*Math.PI);
                 ctx.strokeStyle='white';
                 ctx.lineWidth=15;
                 ctx.stroke();

                 ctx.beginPath();
                 ctx.arc(100,100,90,-90*Math.PI/180,198*Math.PI/180);
                 ctx.strokeStyle='black';
                 ctx.lineWidth=15;
                 ctx.stroke();
                
                var str='80%'
                ctx.font='50px SimHei';
                ctx.fillStyle='black';
                ctx.textBaseline='middle';
                var width=ctx.measureText(str).width
                ctx.fillText(str,100-width/2,100)
            }
        }
    }
</script>

<style scoped>
    #touxiang{
        width:100%;
        background:#02cad4;
    }
    #touxiang>div:first-child{
        width:970px;
        height:630px;
        padding-right: 15px;
        padding-left: 15px;
        margin-right: auto;
        margin-left: auto;
        margin-top:70px;
    }
    #touxiang:before{
        display:table;
        content:''
    }
    #touxiang>div{
        position:relative;
    }
    #touxiang>div>div:first-child{
        display:inline-block;
        width:400px;
        position:absolute;
        top:150px;
        right:100px;
    }
    #touxiang>div>div>p:nth-child(1){
        font-size:23px;
        text-align: right;
        margin:10px 0 0;
        font-weight: 500;
        line-height:1.1;
    }
    #touxiang>div>div>p:nth-child(2){
        font-size:60px;
        text-transform: uppercase;
        color:#fff;
        text-shadow:5px 5px 0 #5d5d5d;
        font-family: 'Text Me One', sans-serif;
        text-align: right;
        line-height:1.4;
        font-weight: bold;
    }
    #touxiang>div>div>p:nth-child(3){
        font-size:28px;
        text-align: right;
        color:#464646;
        margin:0 0 20px;
        font-style:italic;
        font-family: inherit;
        font-weight: 500;
        margin-top:10px;
        line-height: 1.1;
    }
    #touxiang>div>div>p:nth-child(4){
        color:#eaeaea;
        font-size:16px;
        line-height:28px;
        text-align: right;
    }
    #about_me{
        padding:70px 0;
    }
    #about_me>div{
        width:970px;
        height:430px;
        padding-right: 15px;
        padding-left: 15px;
        margin-right: auto;
        margin-left: auto;
    }
    #about_me>div>h3{
        text-align: center;
        color:#1b242f;
        text-transform: capitalize;
        font-family: 'Oswald', sans-serif;
        font-size:35px;
        line-height:1.1;
        font-weight:bold;
    }
    #about_me>div>div:nth-child(2)>div{
        width:90px;
        height:80px;
        float:left;
        text-align: center;
        margin-left:90px;
        margin-top:30px;
        padding-bottom:50px;
    }
    #about_me>div>div:nth-child(2)>div img{
        display: inline-block;
        height:70px;
        padding-bottom:15px;
        border-bottom:1px solid black;
    }
    #about_me>div>div:nth-child(2)>div h4{
        margin-top:10px;
        color:black;
        font-size:17px;
        letter-spacing:1px;
        font-weight:600;
        text-transform: uppercase;text-align: center;
    }
    #about_bottom{
        margin-top:30px;
        float:left;
        width:100%;
    }
    #about_bottom>div:nth-child(1){
        display: inline-block;
        width:250px; 
        margin-left:20px;
        position:relative;
        bottom:20px;
    }
    #about_bottom>div:nth-child(1) h4{  
        font-size:16px;
        color:black;
        font-weight:600;
        font-style:italic;
        letter-spacing: 2px;
        text-transform: uppercase;
        font-family: inherit;
        line-height:40px;
        vertical-align: top;
    }
    #about_bottom>div:not(:nth-child(1)){
        display: inline-block;
        margin-left:20px;
        width:330px; 
    }
    #about_bottom>div:not(:nth-child(1)) p{
        font-size: 14px;
        line-height: 30px;
        text-align: left;
        color: #4c4c4c;
        font-family: 'Open Sans', sans-serif;
    }
    #click_button{
        display: block;
        width:300px;
        height:40px;
        border:3px solid white;
        border-radius: 10px;
        text-align: center;
        line-height:40px;
        margin:0 auto;
        position:relative;
        top:530px;
        animation: click_button 2s infinite;
        animation-direction: normal;
        }
    #touxiang>div>a{
        background:transparent;
        text-decoration: none;
        font-weight:bold;
        font-size:30px;
    }
   #touxiang>div>a p{
        display:inline-block;
        width:15px;
        height:15px;
        border:3px solid white;
        border-left:none;
        border-top:none;
        transform: translateY(-5px) rotate(45deg) 
    }
    #demo{
        width:100%;
        background:#1e2938;
    }
    #demo::after{
        display: block;
        content:'';
        clear:both;
    }
    #demo>div{
        width:970px;
        margin:0 auto;
    }
    #demo>div::before{
        display: table;
        content:'';
    }
    #demo>div>h3{
        color:white;
        text-transform: capitalize;
        font-family: 'Oswald', sans-serif;
        font-size:35px;
        text-align: center;
        font-weight:bold;
        margin:40px 0;
    }
    #demo>div>ul{
        display: block;
        width:970px;
        height:30px;
        list-style: none;
        margin:0 auto;
    }
    #demo>div>ul>li{
        float:left;
        text-align: center;
        margin-left:150px;
    }
    #demo>div>ul>li>a{
        text-decoration: none;
        color:white;
        font-size:19px;
    }
    #demo_bottom{
        width:970px;
        margin:0 auto;
    }
    #demo_bottom ul{
        list-style:none;
    }
    #demo_bottom ul li{
        float:left;
        width:200px;
        height:300px;
        border:1px solid red;
        overflow: hidden;
        margin-left:40px;
        margin-top:15px;
        cursor: pointer;
    }
    #demo>div>ul>li:nth-child(1)>a{
        font-size:20px;
        font-weight: bold;
    }
    #demo>div>ul>li>a:hover{
        color:#10A7AF;
    }
    .demo_font_active{
        color:#10A7AF !important;
    }
    #demo_bottom ul li img{
        height:300px;
        position:relative;
        right:180px;
        transition:1s;
    }
    #demo_bottom ul li{
        margin-bottom:10px;
    }
    .demo_bottom_img_hover{
        height:330px;
        position:relative;
        right:200px;
        cursor: pointer;
    }
    #demo_content_1{
        width:100%;
        height:1000px;
        background:rgba(0,0,0,.8);
        position:fixed;
        top:0px;
        left:0px;
        right:0px;
        z-index:1000;
        text-align: center;
    }
    #demo_content_1 img{
        padding-top:40px;
        height:400px;
    }
    #demo_content_1 h1{
        color:white;
        display: block;
        width:970px;
        margin:0 auto;
        margin-top:50px;
        line-height:40px;
        font-weight: 500;
        font-size:60px;
    }
     #demo_content_1 h3{
        color:white;
        display: block;
        width:970px;
        margin:0 auto;
        margin-top:50px;
        line-height:40px;
        font-weight: 500;
     }
      #demo_content_1 button{
          color:white;
          font-size:25px;
          background: transparent;
          padding:10px;
          border-radius: 10px;
          cursor: pointer;
          position:absolute;
          top:50px;
          right:200px;
      }
      #bg_img{
        width:100%; 
        height:400px;
        background:url('../assets/3.jpg') no-repeat;
        background-position: 50% -100px;
        background-attachment:fixed;
        opacity: 0.9;
        position:relative; 
      }
      #bg_data{
        width:100%; 
        height:550px;
        background:url('../assets/1.jpg') no-repeat;
        background-position: 70% -250px;
        background-attachment:fixed;
        opacity: 0.9;
        position:relative; 
      }
      #bg_img ul{
          position:relative;
          top:20%;
          text-align: center;
          list-style: none;
          font-size:30px;
      }
      #bg_img ul li{
          float:left;
          margin-left:200px;
      }
      #bg_img ul li h2{
          font-size:28px;
          color:firebrick;
      }
      #bg_img ul li p{
          margin-top:20px;
          font-size:80px;
          color:indigo;
      }
      #jiaoyu{
          width:100%;
      }
      #jiaoyu>div{
          width:970px;
          margin:0 auto;
      }
      #jiaoyu>div>h3{
          text-align: center;
          padding:40px 0; 
          font-size:35px;
      } 
      #jiaoyu>div>h4{
          text-align: center;
          font-size:30px;
          padding:20px 0;
      }
      #jiaoyu>div>h4:last-child{
          margin-top:50px;
      }
      #jiaoyu>div>div>div{
          border:1px solid #CACACA;
      }
      #jiaoyu>div>div>div>span{
        font-size:14px;
        margin:0 9px 14px 0;
        color:#929292;
        text-transform: uppercase;
        font-family: 'Text Me One', sans-serif;
        font-weight: 600;
        line-height:50px;
        margin-left:50px;
      }
      #jiaoyu>div>div>div>p{
        color:#23527c;
        display: inline-block;
        border-bottom: 1px solid #CACACA;
        background: #fff;
        transition: all linear 0.15s;
        font-size: 20px;
        text-indent: 2em;
        padding: 31px 0;
        text-transform: uppercase;
        font-family: 'Text Me One', sans-serif;
        font-weight: 600;
        cursor: pointer;
      }
      #jiaoyu>div>div>div::before{
          display:table;
          content:'';
      }
      #jiaoyu>div>div>div>h3{
        font-size: 20px;
        margin-bottom: 15px;
        font-family: 'Text Me One', sans-serif;
        color: #000;
        font-weight: 600;
        padding-top:20px;
        margin-left:20px;
      }
      #jiaoyu>div>div>div>h4{
        display:block;
        width:800px;
        margin:0 auto;
        text-indent: 2em;
        line-height: 1.5em;
        cursor: pointer;
        color: #464646;
        text-decoration: none;
        font-size: 15px;  
        transition:.5s all;
        background-color: transparent;
        padding-bottom:20px;
      }
      #work{
          width:100%;
          border:none !important;
          margin-bottom:20px;
      }
      #work::after{
          display: block;
          content:'';
          clear:both;
      }
      .work>div:first-child{
          width:20%;
          float:left;
          background:#02bdc6;
          text-align:center;
          padding:2em 0;
          border:2px solid #02bdc6;
          transition:.5 all;
      }
      .work>div:first-child p{
        font-size:20px;
        color:white;
        font-family: 'Text Me One', sans-serif;
        font-weight: 500;
        line-height: 1.1;
      }
      .work>div:first-child h3{
        font-size: 1.5em;
        color: #fff;
        margin-top: 1em;
        font-family: 'Text Me One', sans-serif;
        font-weight: bold;
        line-height: 1.1;
        text-align: center;
      }
      .work>div:last-child{
        float: right;
        width: 65%;
        border: 1px solid #02bdc6;
        padding: 2em 4em;
      }
      .work>div:last-child h3{
        font-size: 1.6em;
        color: #1dadd3;
        margin-bottom: 0.5em;
        font-family: 'Text Me One', sans-serif;
        font-weight: bold;
        line-height: 1.1;
      }
      .work>div:last-child p{
        color: #464646;
        line-height: 30px;
        font-size: 14px;  
        font-family: 'Open Sans', sans-serif;
      }

      #c1,#c2,#c3,#c4{
          background:transparent;
      }
      #bg_data>ul:first-child{
        position:absolute;
        right:0px;
        list-style:none;
      }
      #bg_data>ul:last-child{
        position:absolute;
        top:280px;
        right:0px;
        list-style: none;
      }
      #bg_data ul li{
          float:right;
          margin-top:20px;
          margin-right:50px;
      }
      #bg_data ul li h4{
          text-align: center;
          font-size:25px;
      }
      .hide{
          display:none;
          float:right;
          margin-right:100px;
          margin-top:50px;
      }
      #contact_me{
          width:100%;
      }
      #contact_me:after{
          display:block;
          content:'';
          clear:both;
      }
      #contact_me>div{
          width:970px;
          margin:0 auto;
      }
       #contact_me>div>div{
           float:left;
           width:200px;
           text-align: center;
           margin-left:95px;
           margin-top:10px;
           margin-bottom:20px;
       }
       #contact_me>div>div>h2{
           font-size:23px;
           padding:10px 0;
       }
       #contact_me>div>div>p{
           font-size:15px;
           line-height:2;
       }
       #contact_me>div>h2{
           text-align: center;
           font-size:40px;
           padding-top:30px;
       }
       #thanks{
           width:100%;
           height:100px;
           background:#1e2938;
       }
       #thanks p{
           font-size:24px;
           color:white;
           text-align: center;
           line-height:100px;
       }
    @keyframes click_button {
        0%{
            transform: translateY(0)
        }
        50%{
            transform: translateY(-20px)
        }
        100%{
            transform: translateY(0)
        }
    }
</style>