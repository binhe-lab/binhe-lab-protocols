# binhe-lab-protocols
Welcome to the wiki page for protocols and tutorials in the GRE lab. To go back to the lab website, click [here](https://binhe-lab.org)

Other than this site, Bin has some protocols that are stored on his [Google Drive](https://drive.google.com/open?id=0BzL_Etr6O7DMZDI4YmQ3MzQtZWNjMS00NDMwLWI0ZmItYjA0ZDQ4ZDg5NGVk). 

{% comment %}
#
#  from https://gist.github.com/Phlow/57eb457898e4ac4c4a20
#  Change date order by adding '| reversed'
#  To sort by title or other variables use {% assign sorted_posts = category[1] | sort: 'title' %}
#
{% endcomment %}

{% assign sorted_cats = site.categories | sort %}
{% for category in sorted_cats %}
{% assign sorted_posts = category[1] | sort: 'title' %}
<h2 id="{{category[0] | uri_escape | downcase }}">{{category[0] | capitalize}}</h2>
<ul>
{% for post in sorted_posts %}
<li><a href="{{ site.url }}{{ site.baseurl }}{{  post.url }}">{{  post.title }}</a></li>
{% endfor %}
</ul>
{% endfor %}
