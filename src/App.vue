<template>
<div id="app">
    <div class="container-fluid">
        <!-- Row start -->
        <div class="row">
            <div class="div-player col-md-8">
                <!-- <iframe id="player" src="http://www.youtube.com/embed/M7lc1UVf-VE?enablejsapi=1" frameborder="0"></iframe> -->
                  
                  <youtube :video-id="videoId" ref="youtube" @playing="_videoPlaying" id="player"></youtube>
            </div>
            
                <div class="div-chat col-md-4">
                    <div class="panel panel-primary">
                        <!--chat box [START]-->
                        <div class="panel-body" id="chat-box">
                            <ul class="chat">
                                <li class="chat-body" v-for="chat in chats" :key='chat.id' @dblclick="likeComment(chat.id)">
                                    <div class="row col-md-12">
                                        <div class="col-md-2">
                                            <img src="http://placehold.it/50/55C1E7/fff&text=U" alt="User Avatar" class="img-circle" />
                                            
                                        </div>
                                        <div class="col-md-10">
                                            <div class="header">
                                                <strong class="primary-font">{{chat.user}}</strong> 
                                                <small class="text-muted">{{chat.date|dateFilter}}</small>
                                                <small>좋아요</small>
                                            </div>
                                            <p>
                                                {{chat.comment}}
                                            </p>
                                            <small>{{chat.playtime|playtimeFilter}}</small>
                                        </div>
                                        <div class="dropdown-chat">
                                            <a href="#">유저정보</a>
                                            <a href="#">신고</a>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </div>
                        <!--chat box [END]-->
                        <!--chat input [START]-->
                        <div class="panel-footer">
                            <div class="row">
                                <div class="col-md-2">
                                    <img src="http://placehold.it/50/b3a2a4/fff&text=ME" alt="User Avatar" class="img-circle" />
                                </div>
                                <div class="col-md-10">
                                    <div class="header">
                                        <strong class="primary-font">UserName</strong> 
                                        <input type="number" class="" id=""/>
                                    </div>
                                    <div>
                                            <div class="input-group">
                                            <input id="btn-input" type="text" class="form-control input-sm" placeholder="Type your message here..." />
                                            <span class="input-group-btn">
                                                <button class="btn btn-warning btn" id="btn-chat">
                                                    Send</button>
                                            </span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <!--chat input [END]-->
                    </div>
                </div>
                
            
        </div>
        <!-- Row end -->
        <div class="col-md-12 div-box">
            <div class="row user-info">
                <img src="http://placehold.it/50/123a81/fff&text=HS" alt="User Avatar" class="img-circle" />
                <div class="nname">
                    <h5>{{name}}</h5>
                    <small>{{date|dateFilter}}</small> 
                </div>
            </div>
            <div class="row">
                <h5>{{title}}</h5>
            </div>
            <div class="row">
                <p>{{description}}</p>
            </div>
            <div class="row">
                <div class="col-md-6">
                    <small class="video_hit">조회수 {{hit}} 회</small>
                </div>
                <div class="col-md-3">
                    <button class=""></button>
                </div>
                <div class="col-md-3">
                    <button class=""></button>
                </div>
            </div>
        </div>
        <div class="col-md-12 div-box">
            
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'app',
    data:()=>({
    title:"title test",
    date:"2018-01-28 10:22:00",
    hit:1246,
    description:"Lorem ipsum dolor sit amet.",
    name:"hakseung",
    chats:[
        {
            id:1,
            user:"Jack",
            playtime:12,
            date:"2018-01-29 11:30:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        },
        {
            id:2,
            user:"Jordan",
            playtime:16,
            date:"2018-01-28 14:43:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        },
        {
            id:3,
            user:"Evan",
            playtime:26,
            date:"2018-01-30 14:20:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        },
        {
            id:4,
            user:"Andrew",
            playtime:36,
            date:"2018-01-25 14:21:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        },
        {
            id:5,
            user:"Jason",
            playtime:42,
            date:"2018-01-30 17:23:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        },
        {
            id:6,
            user:"Peter",
            playtime:62,
            date:"2018-01-30 17:45:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        },
        {
            id:7,
            user:"Sam",
            playtime:82,
            date:"2018-01-29 17:54:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        },
        {
            id:8,
            user:"Peter",
            playtime:88,
            date:"2018-01-30 18:04:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        },
        {
            id:9,
            user:"Chris",
            playtime:92,
            date:"2018-01-30 12:14:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit."
        },
        {
            id:10,
            user:"Emily",
            playtime:114,
            date:"2018-01-30 19:13:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        },
        {
            id:11,
            user:"Tom",
            playtime:152,
            date:"2018-01-30 20:15:00",
            comment:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
            +"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
            +"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur bibendum ornare dolor, quis ullamcorper ligula sodales."
        }        
    ],
        videoId: 'lG0Ys-2d4MA'
    }),
    methods:{
        likeComment:function(id){
            //좋아요
            alert("like "+id);
        },
        //[START : video state]
        _videoEnded:()=>{
            clearInterval();
        },
        _videoPlaying:()=>{
            setInterval(() => {
               console.log(this.player.getCurrentTime());
            }, 100);
        },
        _videoPaused:()=>{
            clearInterval();
        },
        _videoBuffering:()=>{
            
        },
        _videoCued:()=>{

        },
        
        //[END : video state]
    },
    computed: {
        player () {
            return this.$refs.youtube.player
        }
    },
    mounted(){
    //scroll down
        var msgList=document.getElementById("chat-box");
        console.log(msgList.scrollTop);
        msgList.scrollTop=msgList.scrollHeight;
    
    },
   
    filters:{
        dateFilter:function(value){
            var time=(new Date()-new Date(value))/1000;
                switch(true){
                case time<60:
                    return "방금";
                case time<60*60:
                    return Math.floor(time/60)+"분 전";
                case time<60*60*12:
                    return Math.floor(time/3600)+"시간 전";
                default:
                    return value;
            }
        },
        playtimeFilter:function(sec){
            var hours = Math.floor(sec / (60 * 60));

            var divisor_for_minutes = sec % (60 * 60);
            var minutes = Math.floor(divisor_for_minutes / 60);

            var divisor_for_seconds = divisor_for_minutes % 60;
            var seconds = Math.ceil(divisor_for_seconds);

            var result = (hours < 10 ? "0" + hours : hours);
            result += ":" + (minutes < 10 ? "0" + minutes : minutes);
            result += ":" + (seconds  < 10 ? "0" + seconds : seconds);
            return result;
        }
        
    }
   }
</script>

    <style>
    @import url('assets/css/App.css');
    </style>
