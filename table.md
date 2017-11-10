---
layout: page
title: About
---
{% assign items = site.data.fridayletters %}

<link href="https://unpkg.com/vanilla-datatables@latest/dist/vanilla-dataTables.min.css" rel="stylesheet" type="text/css">
<script src="https://unpkg.com/vanilla-datatables@latest/dist/vanilla-dataTables.min.js" type="text/javascript"></script>

# Browse Friday Letters

<table id="letter-table" class="display">
    <thead>
        <tr>
            <th>Date</th>
            <th>Subject</th>
            <th>Body</th>
        </tr>
    </thead>
    <tbody>
{% for item in items %}        
        <tr>
            <td>{{ item.date }}</td>
            <td>{{ item.title }}</td>
            <td>{{ item.body | strip_html | truncatewords: 15 }}<br><a href="{{ site.baseurl }}/letters/{{ item.date }}.html">Read</a></td>
        </tr>
{% endfor %}
    </tbody>
</table>

<script>
    var dataTable = new DataTable("#letter-table", {
        perPage: 20,
    });
</script>
