<nav style="padding: 0.25em 1em; background: #f4f4f4; border-radius: 0.25rem; text-align: center; border: 2px solid #f4f4f4; color:black;">
<div style="margin: -1em 0">

{% liquid
assign n = name | default: 'sht1' | split: '/' | last
assign prefixes = 'Coverage,FAQ,Feedback,OrganizerNotes,Sponsorship' | split: ','
-%}
**{% render 'Event', name: name %}**
{%- liquid
for prefix in prefixes
  assign p = prefix | append: '/' | append: n | get_page
  if p.exists
    echo ' &middot; [' | append: prefix | append: '](/wiki/' | append: p.ref | append: ')'
  endif
endfor
%}

</div>
</nav>