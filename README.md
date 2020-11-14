# ParseEdisonElectionData
C# Program to Parse and Analyze the Edison real time json feed of 2020 Presidential Election Voting

Yesterday, 2020-11-12, I wrote a one-file C# program to analyze the 2020 Presidential Election data
stream produced by EDISON and archived by the NYTIMES and analyzed in python by "Centipede" at some
TheDonald.win, which made huge claims of fraud, but I am much more cautious.

Today, to share the code and the data output, I am creating this public GITHUB account, at URL
https://github.com/IneffablePerformativity/ParseEdisonElectionData

I found the archived input data to be dirty, and needed to massage it and excuse many artifacts.

Here is a one-off anomaly, that I attribute to a non-atomic update of computed data, in the
Nebraska data: See the reported percentages took a huge hit for one sample, then recovered.
   926348 votes,    0.587 % trump,    0.391 % biden, 2020-11-06T15:11:02Z
   940208 votes,    0.617 % trump,     0.36 % biden, 2020-11-07T00:44:14Z
   940208 votes,    0.585 % trump,    0.391 % biden, 2020-11-07T00:47:20Z

After that, consider how candidate percentage is only saved to 3 decimal places. Every slip of
just 0.001 on say, a 1,000,000 vote current total results in a jump up, OR DOWN, of 1000 votes.

So far, I have only analyzed for two sorts of possible fraud:
1. Whenever the total count of votes, being reported as an integer, decreased!. ?!?!?!
2. Whenever the candiate count decreased BEYOND the effect of round off errors. !?!?!?
3. And, out of curiosity, naive candidate decreases without regard to round off errors.

I, BEING IGNORANT OF THE PROCESS, CANNOT IMAGINE WHY VOTE TOTALS SHOULD EVER DECREASE!

The net effect during such provable events was actually beneficial to Trump, not Biden.

However, the ~ 100 decreases of total counts may have been making room for other fraud.

The worst percentage of final vote margin effect by state was in Pennsylvania:

Pennsylvania had 7 provable flaws, worth 495% of the final vote margin.
...
11/3/2020 8:14:32 PM: dTotalVotes = -239804, dTrumpVotes = -42326, dBidenVotes = -196432
11/3/2020 8:17:03 PM: dTotalVotes = -114886, dTrumpVotes = -127916, dBidenVotes = 12400
11/3/2020 8:22:45 PM: dTotalVotes = -586189, dTrumpVotes = -145179, dBidenVotes = -416589
...
Biden won by 54501 votes while Trump was given 270316 net votes while 941172 votes disappeared in pennsylvania.

Remember, I so far only took a very narrow view of what I hoped might be proven as fraud.
