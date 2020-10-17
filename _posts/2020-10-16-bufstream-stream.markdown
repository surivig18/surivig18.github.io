---
layout: post
title:  "IO Buffered Reader vs NIO File Reader using Streams"
date:   2020-10-16 22:19:12 +0800
categories: jekyll update
---
File Reading in java has different options. Just trying to compare the time taken for reading a file from disk using 
 

`Directly using buffered reader`



{% highlight ruby %}
        FileReader fileReader = new FileReader("*.csv");
            BufferedReader inStream = new BufferedReader(fileReader);

            while(inStream.readLine()!= null)
            {
                System.out.println(inStream.readLine());
            }
{% endhighlight %}

Time taken to process : 3 min 22 sec

`NIO Files using Streams`

{% highlight ruby %}
        Stream<String> lines = Files.lines(Paths.
                    get("*.csv"));
             lines.forEach(l -> {
                System.out.println(l);
            });
            }
{% endhighlight %}
Time taken for process : 8 min 11 sec

A short analysis coming soon !

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
