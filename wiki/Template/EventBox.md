{% liquid
assign n = name | default: 'sht1'
assign base = 'Events/' | append: n | getpage
%}
{{ base.data.name | default: n }}