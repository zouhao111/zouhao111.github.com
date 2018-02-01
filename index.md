---
layout: home
---
<style type="text/css" media="screen">
  .container {
    margin: 13px auto;
    max-width: 800px;
    max-height: 420px;
    
    font-family:Verdana; 
   /* text-align: center;*/
    background:url(../resouse/img/timg3.jpg) no-repeat 180px 0px;

  }
  h1 {
    margin: 30px 0;
    font-size: 4em;
    line-height: 1;
    letter-spacing: -1px;
  }
</style>


<div class="container">

<h1 style="font-style:italic;font-family: Georgia;">Welcome to here</h1>
<br>
<br>
<br>
<br>
<br>
<br>
<p>If you want to find something, search below</p>
<input class="page-search-input" type="text" placeholder="搜索" />
 </div>
<script type="text/javascript">
	
	document.querySelector('.page-search-input').addEventListener('keyup',function(e){
    var archive = document.getElementsByClassName('archive-item-link');

    for (var i = 0; i < archive.length; i++){
    	
        if( archive[i].title.toLowerCase().indexOf(this.value.toLowerCase()) > -1 ) {
            archive[i].closest('li').style.display = '';
        } else {
            archive[i].closest('li').style.display = 'none';
        }
        if(this.value.toLowerCase()==""){archive[i].closest('li').style.display = 'none';}

    }
    if(e.keyCode == 13){
       
    }
})

</script>
{% for post in site.posts %}
{% unless post %}
{% else %}
{% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
{% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
{% if year != nyear %}

{:class="archive-title"}
{% endif %}
{% endunless %}
* {{ post.date | date: "%y-%m-%d" }} &raquo; [{{ post.title }}]({{ post.url }} "{{ post.title }}"){:.archive-item-link}
{% endfor %}
<script type="text/javascript">
	var archive2 = document.getElementsByClassName('archive-item-link');
	for (var i = 0; i < archive2.length; i++){
		archive2[i].closest('li').style.display = 'none';
	}

</script>

