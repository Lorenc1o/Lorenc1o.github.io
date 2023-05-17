---
layout: base
---
<head>
    <link rel="stylesheet" href="/assets/css/mystyle.css">
</head>
<div class="sidebar">
    <h2>Table of Contents</h2>
    <select id="toc-select">
        <!-- options will be added by JavaScript -->
    </select>
    <ul id="toc-list">
        <li><a href="#about">About</a></li>
        <li><a href="#education">Education</a></li>
        <li><a href="#work-experience">Work Experience</a></li>
        <li><a href="#languages">Languages</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#hobbies">Hobbies</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</div>
<script>
document.addEventListener('DOMContentLoaded', function() {
    var tocSelect = document.getElementById('toc-select');
    var tocList = document.getElementById('toc-list');

    // Create an <option> for each <li> in the table of contents
    for (var i = 0; i < tocList.children.length; i++) {
        var li = tocList.children[i];
        var option = document.createElement('option');
        option.value = li.querySelector('a').href;
        option.textContent = li.textContent;
        tocSelect.appendChild(option);
    }

    // Navigate to the selected section when an option is selected
    tocSelect.addEventListener('change', function() {
        window.location = tocSelect.value;
    });
});
</script>
<div class="main-content">
    {{ content }}
</div>
