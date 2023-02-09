## Grep -n

* The 'grep -n' command extends the basic functionality of grep by allowing users to search for a specific word or phrase in a text file or directory, and display the line number of each occurrence. Unlike traditional grep, which only outputs the content of the line containing the match, the '-n' flag provides the line number in addition to the matching text. 

```
grep -n -r "theater" written_2
written_2/non-fiction/OUP/Berk/CH4.txt:207:Filmstar Charlie Chaplin’s mother was herself a talented comedy actress and singer. As a young child, Charlie often accompanied her when she went to work at the theater. As a result, playacting and impersonating became an early focus of Charlie’s pretending. One evening during a performance, his mother’s voice failed. In a pinch, the stage manager, who had seen Charlie at play, led the little boy onstage in her place. Charlie continued his playacting unabated, which included songs, dances, and impersonations from his mother’s repertoire. He was demonstrating the wares of his ﬁrst and best teacher in the art of make-believe, and the performance evoked a roar of appreciation and a shower of coins from the crowd.55
```
* So, when searching for the word 'theater' in a directory that contains multiple instance, grep -n will return not only the lines containing the word, but also the line numbers for each occurrence.

```
grep -n -r "Indoor skating" written_2
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt:54:Ice-skating. Beihai Park and the Summer Palace both offer superb outdoor ice-skating in the winter, with skate rental at stalls on the shoreline. Indoor skating is available at the Ditan Ice Arena in Ditan Park and at the underground shopping center connecting the Traders and China World hotels (1 Jianguomenwai Dajie).
```
* When searching for the word 'Indoor skating' in a text file located within a nested directory, the grep -r -n command is used to ensure comprehensive results. The -r option enables a recursive search, allowing grep to search through all subdirectories. The -n option, as previously explained, displays the line number for each line that contains a match. With these options, the output not only shows the instances of the word 'Indoor skating', but also the specific line numbers where they are located.

## Grep -w

* The 'grep -n' command extends the basic functionality of grep by searching for exact word matches in text files. The -w option stands for "word", and it instructs grep to search for only complete and exact word matches. In contrast, without the -w option, grep will return results for partial matches and substrings that contain the search term. 

```
grep -w "199" /Users/lindalee/skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch1.txt
```

```
grep "199" /Users/lindalee/skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch1.txt 
The most surprising aspect of this story is that today’s U.S. apparel and textile industries—left for dead by business commentators and economic analysts in the 1980s—have begun to transform themselves, reaping new competitive advantages. Although Bond Stores’ customers were thrilled by a suit with two pairs of pants, contemporary customers want and expect a huge range of choices, and the consumer desire for limitless variety has kept the American apparel industry alive. In 1995, for instance, American consumers purchased 28.7 outerwear garments (all coats, jackets, shirts, dresses, blouses, sweaters, trousers, slacks, and shorts) per capita; in China the estimated number of such garments was only 2 per capita.2
```
* For example, a traditional grep search for "199" would return matches for "1996", "1997", and "1998", but with the -w option, there would be no matches as there are no complete words in the text file that exactly match "199".

```
grep -w "(NAFTA)" /Users/lindalee/skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch1.txt
Trade data already suggest a major restructuring in the sources of U.S. apparel imports. The surge in apparel imports in the 1980s came from low-wage countries, primarily the Asian “Big Four”—the People’s Republic of China, Hong Kong, Taiwan, and Korea. This group of nations provided 39 percent of all apparel imports in 1964 and 51 percent of all apparel imports by 1988 (measured in square-meter equivalents, a measure of quantity). But by 1996, the Big Four’s share of imports had fallen to 26 percent. Their U.S. share has been increasingly displaced by those of Mexico and Caribbean nations.35 Although these shifts in part reflect changes in U.S. trade policy, such as the North American Free Trade Agreement (NAFTA), they fundamentally arise from new sourcing patterns attributable to channel integration and the consequent need for apparel items that can be delivered in a shorter time to the U.S. market.
```

```
grep -w "NAFTA" /Users/lindalee/skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch1.txt
Trade data already suggest a major restructuring in the sources of U.S. apparel imports. The surge in apparel imports in the 1980s came from low-wage countries, primarily the Asian “Big Four”—the People’s Republic of China, Hong Kong, Taiwan, and Korea. This group of nations provided 39 percent of all apparel imports in 1964 and 51 percent of all apparel imports by 1988 (measured in square-meter equivalents, a measure of quantity). But by 1996, the Big Four’s share of imports had fallen to 26 percent. Their U.S. share has been increasingly displaced by those of Mexico and Caribbean nations.35 Although these shifts in part reflect changes in U.S. trade policy, such as the North American Free Trade Agreement (NAFTA), they fundamentally arise from new sourcing patterns attributable to channel integration and the consequent need for apparel items that can be delivered in a shorter time to the U.S. market.
```
* It's noteworthy that in the text file, there is a word "NAFTA" enclosed in parentheses. Despite this, using grep -w "NAFTA" will still return the content, as it will also match grep -w "(NAFTA)". This demonstrates that grep -w is a special marker-insensitive tool for searching for exact word matches in text files.

## Grep -c

* The 'grep -c’ command extends the basic functionality of grep by printing only a count of the lines that matches a patterns. The '-c' option, which stands for "count," only outputs the number of occurrences of the pattern, without displaying the line numbers or contents. This feature can be useful when searching for the frequency of a pattern in a file or directory.

```
grep -c "Egypt" /Users/lindalee/skill-demo1-data/written_2/travel_guides/berlitz1/WhatToEgypt.txt
39
```

For example by searching grep -c “Egypt” in txt file what to Egypt, the only thing appear is the number of appearance of the word in the file.

```
grep -c "Egypt" /Users/lindalee/skill-demo1-data/written_2/travel_guides/berlitz1/*
/Users/lindalee/skill-demo1-data/written_2/travel_guides/berlitz1/HandRHawaii.txt:0
/Users/lindalee/skill-demo1-data/written_2/travel_guides/berlitz1/HandRHongKong.txt:0
/Users/lindalee/skill-demo1-data/written_2/travel_guides/berlitz1/HandRIbiza.txt:0
/Users/lindalee/skill-demo1-data/written_2/travel_guides/berlitz1/HandRIsrael.txt:0
/Users/lindalee/skill-demo1-data/written_2/travel_guides/berlitz1/HandRIstanbul.txt:0
/Users/lindalee/skill-demo1-data/written_2/travel_guides/berlitz1/HandRJamaica.txt:0 ...
```
* However, when searching a entire directory using /*, not only will the number of files be displayed, but also the count of appearance of the specified pattern in each file. For example, searching for the word "Egypt" in the directory "/berlitz1/" will produce a list of files with the count of occurrences of the word "Egypt" in each file.

## Grep -i

* The 'grep -i’ command extends the basic functionality of grep by ignoring the case of the input word. 

```
(base) lindalee@MacBook-Pro-10 travel_guides % find berlitz1 > ~/all_berlitz1.txt 
(base) lindalee@MacBook-Pro-10 travel_guides % grep -i "WHATTOHONGKONG" ~/all_berlitz1.txt
berlitz1/WhatToHongKong.txt
```
"For example, if you create a file called "all_berlitz1.txt" that contains the names of all files, a search for "WHATTOHONGKONG" using grep will not produce any results, as grep is case-sensitive and there is no exact match for this input. However, using 'grep -i' will produce the expected result, which is "WhatToHongKong".

```
(base) lindalee@MacBook-Pro-10 travel_guides % grep -i "WHATTOIS" ~/all_berlitz1.txt
berlitz1/WhatToIsrael.txt
berlitz1/WhatToIstanbul.txt
```

It's worth noting that the '-i' option differs from the '-w' option in that it doesn't check for an exact match at the word level. As a result, searching for 'grep -i "WHATTOIS"' will return both "WhatToIsrael" and "WhatToIstanbul".

## Acknowledgement

I would like to acknowledge the sources that I have referred to including ChatGPT, the 'man grep' manual page, and the website GreekForGreek.

* Specifically, here is a question I asked to chatGPT and here is its response. 
![ChatGPT](Images/ChatGpt.png)

Additionally, here is the link to the GreekForGreek website: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

