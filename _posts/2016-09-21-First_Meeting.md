---
layout: post
title: First Meeting
date: 2016-09-23
---

We had our first meeting on Friday. We watched the kickoff video, which you can
find on the [links section](/links/) of this page.  We looked at the last year's
robot, (pictures of which you can find on the [about section](/about/) of this
page.  We had a good discussion about _gracious professionalism_.

The team experimented a bit with _Processing_.  We started with an example
program, and after some editing and experimenting, this is what we had at the
end of the meeting:

```Java
void setup() {
  size(500, 500);
  background(random(255),random(255),random(255));
}

void draw() {
  stroke(random(255),(255),(255),67);
  if (mousePressed == true) {
    line(mouseX + random(100), mouseY + random(100), pmouseX + random(100), pmouseY + random(100));
  }
}
```

Links to download Processing and to processing tutorials are at the [links
section](/links/) as well.

I am looking forward to see everybody on Wednesday at 3:30 in the library
again.
