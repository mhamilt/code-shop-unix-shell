---
layout: workshop # DON'T CHANGE THIS.
carpentry: "swc" # what kind of Carpentry (must be either "lc" or "dc" or "swc").
# Be sure to update the Carpentry type in _config.yml as well.
venue: "CodeShop: The Unix Shell" # brief name of host site without address (e.g., "Euphoric State University")
address: "7-8 Chambers street" # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "UK" # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "English" # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latlng: "55.94800, -3.18753" # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "Friday Jan 17, 2020" # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "09:30 - 11:30" # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate:
enddate:
instructor: ["Matthew Hamilton"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: [""] # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["matt.hamilton@ed.ac.uk"] # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org","ruth.lichterman@example.org"]
collaborative_notes: # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite: # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

<h2 id="general">General Information</h2>

<p>
  This hands-on workshop will cover the principles of using the terminal and BASH.
  We encourage you to help one another
  and to apply what you have learned to your own research problems.
  This tutorial is based on the principles of <a href="{{site.swc_site}}">Software Carpentry</a>, which aims to help researchers get their work done in less time and with less pain by teaching them basic research computing skills.
</p>
<p align="center">
  <em>
    For more information on Software Carpentries,
    please see this paper
    "<a href="http://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1001745">Best Practices for Scientific Computing</a>".
  </em>
</p>

{% comment %}
AUDIENCE

Explain who your audience is. (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
{% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set. You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latlng %}

<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=18">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}

<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}

<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed <a href="#setup">below</a>).
</p>

{% comment%}
CODE OF CONDUCT
{% endcomment %}

<p id="code-of-conduct">
  <strong>Code of Conduct:</strong> Everyone who participates is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident
  if needed.
</p>

{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}

<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance. If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
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

<hr />

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
<div class="row">
  <div class="col-md-12">
  <h3 id="syllabus-shell">The Unix Shell</h3>
  <ul>
    <li>Files and Directories</li>
    <li>History and Tab Completion</li>
    <li>Pipes and Redirection</li>
    <li>Looping Over Files</li>
    <li>Creating and Running Shell Scripts</li>
    <li>Finding Things</li>
    <li><a href="{{site.swc_pages}}/shell-novice/reference">Reference...</a></li>
  </ul>
  </div>

    <!-- <div class="col-md-6">
      <h3 id="syllabus-python">Typesetting in LaTeX</h3>
      <ul>
        <li>Building a LaTeX Project</li>
        <li>Formatting equations and images</li>
        <li>Citations with BibTeX</li>
        <li>Using Packages</li>
        <li><a href="https://en.wikibooks.org/wiki/LaTeX">Reference...</a></li>
      </ul>
    </div> -->
</div>

<hr />

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions. Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<!-- <p>
<strong>OS:</strong> First off, let us know which operating system you are using in <a href="https://doodle.com/poll/gttcbmqn8hr6k58r">this poll</a>. This will make it a lot easier to debug problems in advance
</p> -->
<p>
  To participate in you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href="{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

<hr />

<div id="shell"> {% comment %} Start of 'shell' section. {% endcomment %}
  <h3>The Bash Shell</h3>

  <p>
    Bash is a commonly-used shell that gives you the power to do simple
    tasks more quickly.
  </p>
  <div>

    <ul class="nav nav-tabs nav-justified" role="tablist">
      <li role="presentation" class="active">
      <a data-os="windows" href="#shell-windows" aria-controls="Windows" role="tab" data-toggle="tab">
        <i class="fab fa-windows"></i> Windows
      </a>
      </li>
      <li role="presentation">
      <a data-os="macos" href="#shell-macos" aria-controls="MacOS" role="tab" data-toggle="tab">
        <i class="fab fa-apple"></i> macOS
        </a>
      </li>
      <li role="presentation">
      <a data-os="linux" href="#shell-linux" aria-controls="Linux" role="tab" data-toggle="tab">
        <i class="fab fa-linux"></i> Linux
        </a>
      </li>
    </ul>

    <div class="tab-content">
      <article role="tabpanel" class="tab-pane active" id="shell-windows">
        <a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
        <ol>
          <li>Download the Git for Windows <a href="https://git-for-windows.github.io/">installer</a>.</li>
          <li>Run the installer and follow the steps below:
            <ol>
              {% comment %} Git 2.22.0 Setup {% endcomment %}
              <li>
                Click on "Next" four times (two times if you've previously
                installed Git). You don't need to change anything
                in the Information, location, components, and start menu screens.
              </li>
              <li>
                <strong>
                  Select "Use the nano editor by default" and click on "Next".
                </strong>
              </li>
              {% comment %} Adjusting your PATH environment {% endcomment %}
              <li>
                Keep "Git from the command line and also from 3rd-party software" selected and click on "Next".
                If you forgot to do this programs that you need for the workshop will not work properly.
                If this happens rerun the installer and select the appropriate option.
              </li>
              {% comment %} Choosing the SSH executable {% endcomment %}
              <li>Click on "Next".</li>
              {% comment %} Choosing HTTPS transport backend {% endcomment %}
              <li>Select "Use the native Windows Secure Channel library", and click "Next".</li>
              {% comment %} This should mean that people stuck behind corporate firewalls that do MITM attacks
              with their own root CA are still able to access remote git repos. {% endcomment %}
              {% comment %} Configuring the line ending conversions {% endcomment %}
              <li>
                Keep "Checkout Windows-style, commit Unix-style line endings" selected and click on "Next".
              </li>
              {% comment %} Configuring the terminal emulator to use with Git Bash {% endcomment %}
              <li>
                <strong>
                  Select "Use Windows' default console window" and click on "Next".
                </strong>
              </li>
              {% comment %} Configuring extra options {% endcomment %}
              <li>Leave all three items selected, and click on "Next".</li>
              {% comment %} Configuring experimental options {% endcomment %}
              <li>Do not select the experimental option. Click "Install".</li>
              {% comment %} Installing {% endcomment %}
              {% comment %} Completing the Git Setup Wizard {% endcomment %}
              <li>Click on "Finish".</li>
            </ol>
          </li>
          <li>
            If your "HOME" environment variable is not set (or you don't know what this is):
            <ol>
              <li>Open command prompt (Open Start Menu then type <code>cmd</code> and press <kbd>Enter</kbd>)</li>
              <li>
                Type the following line into the command prompt window exactly as shown:
                <p><code>setx HOME "%USERPROFILE%"</code></p>
              </li>
              <li>Press <kbd>Enter</kbd>, you should see <code>SUCCESS: Specified value was saved.</code></li>
              <li>Quit command prompt by typing <code>exit</code> then pressing <kbd>Enter</kbd></li>
            </ol>
          </li>
        </ol>
        <p>This will provide you with both Git and Bash in the Git Bash program.</p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="shell-macos">
        <p>
          The default shell in all versions of macOS is Bash, so no
          need to install anything. You access Bash from the Terminal
          (found in
          <code>/Applications/Utilities</code>).
          See the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
          for an example on how to open the Terminal.
          You may want to keep
          Terminal in your dock for this workshop.
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="shell-linux">
        <p>
          The default shell is usually Bash, but if your
          machine is set up differently you can run it by opening a
          terminal and typing <code>bash</code>. There is no need to
          install anything.
        </p>
      </article>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}
<hr />

<div id="git"> {% comment %} Start of 'Git' section. {% endcomment %}
  <h3>Git</h3>
  <p>
    Git is a version control system that lets you track who made changes
    to what when and has options for easily updating a shared or public
    version of your code
    on <a href="https://github.com/">github.com</a>. You will need a
    <a href="https://help.github.com/articles/supported-browsers/">supported
      web browser</a>.
  </p>
  <p>
    You will need an account at <a href="https://github.com/">github.com</a>
    for parts of the Git lesson. Basic GitHub accounts are free. We encourage
    you to create a GitHub account if you don't have one already.
    Please consider what personal information you'd like to reveal. For
    example, you may want to review these
    <a href="https://help.github.com/articles/keeping-your-email-address-private/">instructions
      for keeping your email address private</a> provided at GitHub.
  </p>

</div> {% comment %} End of 'Git' section. {% endcomment %}
<hr />
<div id="editor"> {% comment %} Start of 'editor' section. {% endcomment %}
  <h3>Text Editor</h3>

  <p>
    When you're writing code, it's nice to have a text editor that is
    optimized for writing code, with features like automatic
    color-coding of key words. The default text editor on macOS and
    Linux is usually set to Vim, which is not famous for being
    intuitive. If you accidentally find yourself stuck in it, hit
    the <kbd>Esc</kbd> key, followed by <kbd>:</kbd>+<kbd>Q</kbd>+<kbd>!</kbd>
    (colon, lower-case 'q', exclamation mark), then hitting <kbd>Return</kbd> to
    return to the shell.
  </p>

  <h4><i class="fas fa-atom"></i> Atom</h4>
  <p>
    For this session we recommend installing <a href="https://atom.io">Atom</a> as it is a versatile text editor with syntax highlighting available for most programming languages.
  </p>

  <div>
    <ul class="nav nav-tabs nav-justified" role="tablist">
      <li role="presentation" class="active"><a data-os="windows" href="#textedit-windows" aria-controls="Windows" role="tab" data-toggle="tab"><i class="fab fa-windows"></i> Windows</a></li>
      <li role="presentation"><a data-os="macos" href="#textedit-macos" aria-controls="MacOS" role="tab" data-toggle="tab"><i class="fab fa-apple"></i> macOS</a></li>
      <li role="presentation"><a data-os="linux" href="#textedit-linux" aria-controls="Linux" role="tab" data-toggle="tab"><i class="fab fa-linux"></i> Linux</a></li>
    </ul>
    <div class="tab-content">
      <article role="tabpanel" class="tab-pane active" id="textedit-windows">
        <p>
          nano is a basic editor and the default that instructors use in the workshop.
          It is installed along with Git.
        </p>
        <p>
          Others editors that you can use are
          <a href="https://notepad-plus-plus.org/">Notepad++</a> or
          <a href="https://www.sublimetext.com/">Sublime Text</a>.
          <strong>Be aware that you must
            add its installation directory to your system path.</strong>
          Please ask your instructor to help you do this.
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="textedit-macos">
        <p>
          nano is a basic editor and the default that instructors use in the workshop.
          See the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
          for an example on how to open nano.
          It should be pre-installed.
        </p>
        <p>
          Others editors that you can use are
          <a href="https://www.barebones.com/products/bbedit/">BBEdit</a> or
          <a href="https://www.sublimetext.com/">Sublime Text</a>.
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="textedit-linux">
        <p>
          nano is a basic editor and the default that instructors use in the workshop.
          It should be pre-installed.
        </p>
        <p>
          Others editors that you can use are
          <a href="https://wiki.gnome.org/Apps/Gedit">Gedit</a>,
          <a href="https://kate-editor.org/">Kate</a> or
          <a href="https://www.sublimetext.com/">Sublime Text</a>.
        </p>
      </article>
    </div>
  </div>
</div> {% comment %} End of 'editor' section. {% endcomment %}
<hr />
<!-- <div id="editor"> {% comment %} Start of 'LaTeX' section. {% endcomment %}
  <h3>LaTeX</h3>
  <p>
    LaTeX is a high-quality typesetting system designed for the production of technical and scientific documentation.
    LaTeX is the de facto standard for the communication and publication of scientific documents.
  </p>
  <h4><i class="fas fa-globe"></i> Online</h4>
  <p>
    <a href="https://www.overleaf.com/">Overleaf</a> is a great tool for getting started with LaTeX quickly. Sadly, git integration comes at a premium, but the basic LaTeX functionality is free.<br>
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="editor-windows"><i class="fab fa-windows"></i> Windows</h4>
      <p>Check out the <a href="http://miktex.org/">MiKTeX</a> distribution
        and it's associated editor, TeXWorks.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-macosx"><i class="fab fa-apple"></i> macOS</h4>
      <p>The <a href="http://www.tug.org/mactex/">MacTeX</a>
        distribution contains everything you need, including a complete
        TeX system with LaTeX itself and editors to write documents.
      </p>
    </div>

    <div class="col-md-4">
      <h4 id="editor-linux"><i class="fab fa-linux"></i> Linux</h4>
      <p>Check your Linux distributions software source for a TeX
        distribution including LaTeX. You can also
        install the current <a href="https://www.tug.org/texlive">TeX Live distribution</a>
        directly---in fact this may be advisable as many Linux distributions only contain
        older versions of TeX Live, see
        <a href="https://repology.org/metapackage/texlive/versions">Linux TeX Live package status</a>
        for details.</p>
    </div>

  </div>

  <h4><i class="fas fa-atom"></i> Atom</h4>
  <p>
    After you have installed one of the above LaTeX distributions, I would highly recommend using Atom. There are a couple of packages that need to be installed, but the benefits out-weigh the inconvenience. You will need to download the following
    packages:
  </p>
  <ul>
    <li><a href="https://atom.io/packages/latex">Latex</a> compile tool by thomasjo</li>
    <li><a href="https://atom.io/packages/latex-autocomplete">latex-autocomplete</a> by evpok</li>
    <li><a href="https://atom.io/packages/language-latex">Language-LaTeX</a> by area</li>
  </ul>
  <p>
    NB: Windows users may want to download <a href="https://www.tug.org/texlive/acquire-netinstall.html">TexLive</a> if they are having trouble with getting atom to work with LaTeX.
  </p>
  <h3>BibTeX</h3>
  <p>On of the powerful aspects of LaTeX is bibliography management using BibTeX. Bibliography files (\*.bib) are most easily edited and modified using a management system. These graphical user interfaces all feature a database form, where
    information is entered for each reference item, and the resulting text file can be used directly by BibTeX.</p>
  <p>For this session we will be using <a href="http://www.jabref.org">JabRef</a>.</p>
</div> {% comment %} End of 'LaTeX' section. {% endcomment %} -->

<script>
var show_instructions = function() /* Based on https://stackoverflow.com/a/30894829/1802726 */
{
  $('.nav-tabs li').removeClass('active'); //set all nav tabs to inactive
  $('.nav-tabs li a[href*="' + localStorage.os + '"]').closest('li').addClass('active'); //get all nav tabs matching the os and set to active
  $('.tab-pane').removeClass('active'); //set all tabs to inactive
  $('.tab-pane[id*="' + localStorage.os + '"]').addClass('active'); //get all tabs matching the os and set to active
}

if (typeof(Storage) !== "undefined")
{
  if (localStorage.os == "undefined")
  {
    localStorage.os = "windows";
  }
  show_instructions();
}
else
{
  console.log("No localStorage");
}

$('.nav-tabs li a').click(function() /* Based on https://stackoverflow.com/a/30894829/1802726 */
{
  localStorage.os = $(this)[0].dataset.os; //get selected os
  show_instructions();
});
</script>
