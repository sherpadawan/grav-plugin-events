# Events plugin for Grav CMS

This is an events plugin for [Grav CMS](http://getgrav.org).

## Frontmatter usage

```
event:
    start: 01/01/2015 6:00pm
    end: 01/01/2015 7:00pm
    repeat: MWF
    freq: weekly
    until: 01/01/2020
```

The `repeat:` event frontmatter uses the MTWRFSU format.

* M - Monday
* T - Tuesday
* W - Wednesday
* R - Thursday
* F - Friday
* S - Saturday
* U - Sunday

## Vars exposed to Twig

```
event.title
event.route
event.start
event.end
```

## Example use in Twig

```
<ul>
    {% for event in events.findEvents({'repeat':'R'}).sortByTime().get() %}
        <li>
            <span class="time">{{ event.start|date("g:ia") }}</span>
            <span class="title"><a href="{{ event.route }}">{{ event.title }}</a></span>
        </li>
    {% endfor %}
</ul>
```
