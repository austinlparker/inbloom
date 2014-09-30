# inBloom Post Mortem 

You can't throw a virtual rock without hitting someone talking about the transformative powers of "big data". (Incidentally, you can't throw a real rock without hitting someone talking about the transformative powers of "big data" if you're walking around the Informatics department, either). There's been [a few][3] [slight][4] [incidents][5] in the past year that raise the spectre of souless corporate overlords collecting reams of quantified information about people and manipulating or selling it to the highest bidder.

Admittedly, when [inBloom was dreamt up in 2011][1], we were in a more innocent, Snowden-free time. Never the less, over $100 million dollars later, inBloom lays fallen; Supposedly, a victim of concerns about student data privacy - although its supporters would argue that it was slain by neo-luddites unable or unwilling to grasp their vision of a brighter and more connected education that involved a lot of students using iPads.

What happened? inBloom and its originator, the [Shared Learning Collaborative][1] were designed by top educators and administrators. Funding was provided as grants, not as venture capital with profit expectation. [Douglas Levin, executive director of the State Educational Technology Directors Association][2] had this to say upon the death of inBloom:
>"While perhaps ahead of its time, the inBloom vision--and the tools inBloom built to realize it--remain critically important for the K-12 sector to build upon in the future ... I certainly hope that others will step up to fill the void that inBloom will be leaving in its wake."

Of course, inBloom had its detractors, such as [parent activist Leonie Haimson][2], who noted:
>"There are more and more data-mining vendors who, with the help of government officials, foundations, and think tanks, are eager to make money off of student information in the name of "big data" and "personalized" learning, and in the process see parents, if they recognize our existence at all, as ignorant obstacles to their Orwellian plans"

To argue, however, that this is simply a story of concerned parents against technocratic overlords is, I believe, to miss a large point. inBloom was conceived as an [open source product][6], with a community of educators and developers working together to guide the both the implementation and orchestration of the project. I mean, these guys were on _GitHub_, obviously they're open as can b-

![heh][7]

Hm.

## Development

inBloom was primarily interested in creating a distributed, national, data warehouse with a sprawling schema that conformed to educational data frameworks such as the [Learning Registry][8]. The development work for the backend seems to have been developed to the strictures and plan of edSurge/SLC prior to inBloom even being 'a thing'. As noted on [this IMS Global blog post][9], "Open source is not open standards". I would tend to agree, and so would [ESR][10] whose [16 Open Source Development Guidelines][11] were published in the seminal "Cathedral and the Bazaar". There are at least two primary issues I can identify with the software development practices of inBloom - first, the software stack was designed to be a monolithic solution to an already solved problem, and second, community developers were not brought in to the underlying data warehousing application and only offered the ability to write apps on top of the platform that inBloom offered.

### Mo' Money, Mo' Problems

inBloom was a top-heavy organization. Flush with cash, and with a mandate from administrators at the top of the educational ladder, they set out to build a software product that would remove integration challenges between multiple products. This in and of itself is a noble goal, but there were two issues - first, the impetus was not "Let's solve a problem that needs solving" (violating [OSD 1][11], "Every good work of software starts by scratching a developer's personal itch") but "Let's go ahead and build something that no one is asking for because hey, we got the cash and it's a lot easier to just bully everyone else into getting on our side once we've made the backend". Looking at the [inBloom Products and Services Matrix][12] we can see that their launch applications were not only a bit lacking, all of the effort had gone into creating the data store. Without applications that end-users and other community members can both see and utilize, there was little incentive for participation (violating [OSD 12, 18][11]) which almost certianly touched off the backlash from concerned parents. A better plan, perhaps, would have been to involve both educators at a district or school level in the context of developers and contributors from an earlier point and to focus less on the back-end. This would have both helped in finding "itches to scratch" as well as lead to better initial applications and tools that may have eased adoption.

### sChemas Rule Everything Around Me, C.R.E.A.M





[1]: http://en.wikipedia.org/wiki/InBloom "inBloom Wikipedia Entry"
[2]: http://blogs.edweek.org/edweek/DigitalEducation/2014/04/inbloom_to_shut_down_amid_growing_data_privacy_concerns.html "inBloom to Shut Down Amid Growing Data-Privacy Concerns"
[3]: http://www.huffingtonpost.com/2013/06/12/nsa-big-data_n_3423482.html "Huffington Post"
[4]: http://www.theatlantic.com/technology/archive/2014/07/data-science-what-the-facebook-controversy-is-really-about/373770/ "The Atlantic"
[5]: http://www.cbsnews.com/news/has-okcupid-played-with-users-hearts/ "CBS News"
[6]: https://github.com/inbloom "github repository for inBloom"
[7]: rsc/inbloom_githeader.png "screenshot of inbloom github repo"
[8]: rsc/inBloomCETIS.pdf "inBloom to implement Learning Registry and LRMI"
[9]: rsc/AbelBlogPost.pdf "IMS Global Blog Post"
[10]: http://en.wikipedia.org/wiki/Eric_S._Raymond "ESR Wikipedia Entry"
[11]: rsc/Benefits_Guidelines.pdf "OSD Guidelines and Open Source Benefits"
[12]: rsc/inBloom_Products_Services.pdf "inBloom Products"