# memorandum
{% load bootstrap3 %}

<!DOCTYPE heml>
<html lang='en'>

  <head>
	  <meta charset="utf-8">
	  <meta http-equiv="X-UA-Compatible" content="IE=edge">
	  <meta name="viewport" content="width=device-width,initial-scale=1">
	  
	  <title>Meal Planner</title>
	  
	  {% bootstrap_css %}
	  {% bootstrap_javascript %}
  
  </head>
  
  <body>
	  <!-- Static navbar -->
	  <nav class="navbar navbar-default navbar-static-top">
		  <div class="container">
			  
			  <div class= "navbar-header">
				  <button type = "button" class="navbar-toggle collapsed"
				    data-toggle= "collapse" data-target="#navbar"
				    aria-expanded= "false" aria-controls = "navbar">
				  </button>
				  
				  <a class= "navbar-brand" href="{% url 'meal_planners:index' %}">
					  Meal Planner</a>
					  
			  </div>
			  
			  <div id="navbar" class= "navbar-collapse collapse">
				  <ul class="nav navbar-nav">
					  <li><a href = "{% url 'meal_planners:plans' %}">Plans</a></li>
				  </ul>
				  
				  <ul class="nav navbar_nav navbar-right">
					  {% if user.is_authenticated %}
					    <li><a>Hello, {{ user.username }}.</a></li>	 
					    <li><a href="{% url 'users:logout' %}">log out</a></li>
					  {% else %}
					    <li><a href="{% url 'users:register' %}">register</a></li>
					    <li><a href="{% url 'users:login' %}">log in</a></li>
					  {% endif %}  
				  </ul>	  
				  
		      </div><!--/.nav-collapse -->	
		 </div>	  
		</nav>  
		
		<div class="container">
			<div class="page-header">
				{% block header %}{% endblock header %}
			</div>
			<div>
			    {% block content %}{% endblock content %}
			</div>
	    </div> <!-- /container -->		    	  
  </body>
  
</html>  
	  
