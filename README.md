# API-Stackoverflow

# **API Stackoverflow**
- Extract information about Badges

#### **Discussion**

Returns all the badges in the system.

Badge sorts are a tad complicated. For the purposes of sorting (and min/max) tag_based is considered to be greater than named.

This means that you can get a list of all tag based badges by passing min=tag_based, and conversely all the named badges by passing max=named, with sort=type.

For ranks, bronze is greater than silver which is greater than gold. Along with sort=rank, set max=gold for just gold badges, max=silver&min=silver for just silver, and min=bronze for just bronze.

rank is the default sort.

This method returns a list of badges.

- Extract information about Questions


#### **Discussion**

Gets all the questions on the site.

This method allows you make fairly flexible queries across the entire corpus of questions on a site. For example, getting all questions asked in the the week of Jan 1st 2011 with scores of 10 or more is a single query with parameters sort=votes&min=10&fromdate=1293840000&todate=1294444800.

To constrain questions returned to those with a set of tags, use the tagged parameter with a semi-colon delimited list of tags. This is an and constraint, passing tagged=c;java will return only those questions with both tags. As such, passing more than 5 tags will always return zero results.

The sorts accepted by this method operate on the following fields of the question object:

activity – last_activity_date
creation – creation_date
votes – score
hot – by the formula ordering the hot tab
Does not accept min or max
week – by the formula ordering the week tab
Does not accept min or max
month – by the formula ordering the month tab
Does not accept min or max
activity is the default sort.

<center>
<img align="center" src="12.png"     style=" width:400px; padding: 20px; " > 
<center>


It is possible to create moderately complex queries using sort, min, max, fromdate, and todate.
This method returns a list of questions.
