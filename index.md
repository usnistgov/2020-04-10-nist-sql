---
layout: workshop      # DON'T CHANGE THIS.
venue: "NIST Telework Lessons"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Online (as indicated by group leader)"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
#latitude: "90"     # decimal latitude of workshop venue (use https://www.latlong.net/)
#longitude: "180"    # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "April 2020"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
#humantime: "TBD"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2020-04-10      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: TBD        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Dilip Banerjee", "Chandler Becker", "Gretchen Greene", "Josh Taillon"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["TBD"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["dilip.banerjee@nist.gov", "chandler.becker@nist.gov", "gretchen.greene@nist.gov", "joshua.taillon@nist.gov"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}


{% comment %}
8< ============= For a workshop delete from here =============
8< ============================= until here ==================
{% endcomment %}


{% comment %}
Check DC curriculum
{% endcomment %}

{% if site.carpentry == "dc" or site.carpentry == "dc" %}
{% unless site.curriculum == "dc-ecology" or site.curriculum == "dc-genomics" or site.curriculum == "dc-socsci" or site.curriculum == "dc-geospatial" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Data Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>dc-ecology</code>, <code>dc-genomics</code>, <code>dc-socsci</code>, or <code>dc-geospatial</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/who.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latitude and page.longitude %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% elsif page.address %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}
  {% comment %}
  {% include workshop_calendar.html %}
  {% endcomment %}
</p>
{% endif %}

{% comment %}
HOW
Special block for remote sessions explaining the approach.
{% endcomment %}
<p id="how">
  <strong>How:</strong>
  Although specific implementations will vary by cohort and instructor, groups
  will generally meet virtually via a web conferencing tool, and the instructor
  will present with a shared screen to a group of no more than 10 learners.
  Learners will follow along, running commands on their own systems and can
  interact with the instructor and helpers throughout the process.
</p>
<p>
  We appreciate your patience and understanding as moving these sessions to an
  online-only format is a first-time learning experience for us and you alike,
  and hiccups in the process are certain to arise. We will try our hardest to
  ensure a good learning experience regardless of the circumstances, but
  feel free to let us know if you have any suggestions for improvements.
</p>

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> 
  Participants must have a computer with a   Mac, Linux, or Windows operating
  system (not a tablet, iPad, etc.) that they have administrative privileges on.
  They should  have a few specific software packages installed (listed
  <a href="#setup">below</a>). If this is not possible, we can also provide a
  remote <em>virtual desktop</em> that can be used for the session (contact your
  instructor for details), but we prefer that you install the software on your
  NIST machine as a learning exercise.
</p>
<p>
  Due to limited screen "real estate", you may find it easier if you have
  multiple monitors: one for the instructor's display and webinar, and another
  on which to evaluate commands and practice in realtime. If this is not
  possible, another solution is to use a second device (such as a tablet or
  another perhaps personal laptop) to login to the web conference and view the
  instructor, while you follow along interactively on your "main" computer.
</p>

{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody. As the workshop will be conducted entirely online,
  you will be able to participate from the comfort of your teleworking location,
  but please let your instructor know in advance if we can make any
  accommodations to help make learning easier for you.
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>.This document also outlines how to report an incident if needed.
</p>

<p class="text-center">
  <a href="https://goo.gl/forms/KoUfO53Za3apOuOK2">
    <button type="button" class="btn btn-info">Report a Code of Conduct Incident</button>
  </a>
</p>
<hr/>


{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}


{% comment %} 
SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
<p><a href="{{ site.pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

<p>
    The schedule is planned for about 6 hours total of instruction for this topic. The detailed
    schedule will be determined by each instructor and the learners in their cohort,
    and communicated separately. We will be following the curriculum of the
    <a href="{{ site.course_notes }}">{{ site.title }}</a> carpentry
    course, adapted for online teaching.
</p>

{% comment %}
{% if site.carpentry == "swc" %}
{% include swc/schedule.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/schedule.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/schedule.html %}
{% endif %}
{% endcomment %}

<hr/>

{% comment %}
SYLLABUS

Show what topics will be covered.

1. If your workshop is R rather than Python, remove the comment
around that section and put a comment around the Python section.
2. Some workshops will delete SQL.
3. Please make sure the list of topics is synchronized with what you
intend to teach.
4. You may need to move the div's with class="col-md-6" around inside
the div's with class="row" to balance the multi-column layout.

This is one of the places where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">Syllabus</h2>

<div class="alert alert-warning">
  This lesson assumes some familiarity with <a href="https://pages.nist.gov/2020-04-10-nist-shell">Bash Shell</a>.
</div>

{% if site.carpentry == "swc" %}
{% include swc/syllabus.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/syllabus.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/syllabus.html %}
{% endif %}

<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.

Also add some better formatting to these tabs
{% endcomment %}

<style>
  .tab-content > .active {
        background: #f7f7f7;
        border: #ddd solid 1px;
        padding: 1em 1em 0.5em 1em;
  }
</style>

<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if site.carpentry == "swc" %}
  Software Carpentry
  {% elsif site.carpentry == "dc" %}
  Data Carpentry
  {% elsif site.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

{% if site.carpentry == "swc" %}
{% include swc/setup.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/setup.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/setup.html %}
{% endif %}
