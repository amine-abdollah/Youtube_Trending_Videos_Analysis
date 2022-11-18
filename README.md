![Youtube](https://user-images.githubusercontent.com/103464869/198981301-f6403dad-6e67-4480-b7fb-62cce7a11906.png)

# YouTube_Trending_Analytics

This repo contains a full analysis of YouTube's trending videos dataset to provide insights for Content Creators on YouTube and advertisers to make the most of their resources

The insights from this project were presented inside MicroStrategy Workstation. For quick access, a summary of insights & screen shoots is available in this [**Slide Deck**](https://docs.google.com/presentation/d/1cj8jm1yx0AFdngpc1KHVYFfgpCTPsh0aUDGlOP8rPEc/edit?usp=sharing) 

## 1. Objectives
One of main objectives of this project was to support YouTubers and Sponsers to pressing questions. 
### For YouTubers, Questions like: 
1. What is the best time to publish a video on YouTube?
2. What is the most promising categories to create content for?  
3. Is there specific tags and keywords that might increase your views?

### For Sponsers, Questions like: 
1. What is the best channels to sponser on YouTube?
2. What is the most promising categories to sponser?  
3. What videos stay longest in trending?

The product of this analysis is a `Custom Dashboard` for YouTubers and Sponsers to allow them to feed the latest data to the system and be able to make optimal decisions.

## 2. Data Sources

The data analysed in this project are public data from [Kaggle](https://www.kaggle.com/datasets/rsrishav/youtube-trending-video-dataset), based on the work of [_RISHAV SHARMA_](https://www.kaggle.com/rsrishav) who is kindly using YouTube API to retrieve this data daily. 

### **Sample Data** 

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>video_id</th>
      <th>title</th>
      <th>publishedAt</th>
      <th>channelId</th>
      <th>channelTitle</th>
      <th>categoryId</th>
      <th>trending_date</th>
      <th>tags</th>
      <th>view_count</th>
      <th>likes</th>
      <th>dislikes</th>
      <th>comment_count</th>
      <th>thumbnail_link</th>
      <th>comments_disabled</th>
      <th>ratings_disabled</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>s9FH4rDMvds</td>
      <td>LEVEI UM FORA? FINGI ESTAR APAIXONADO POR ELA!</td>
      <td>2020-08-11T22:21:49Z</td>
      <td>UCGfBwrCoi9ZJjKiUK8MmJNw</td>
      <td>Pietro Guedes</td>
      <td>22</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>pietro|guedes|ingrid|ohara|pingrid|vlog|amigos...</td>
      <td>263835</td>
      <td>85095</td>
      <td>487</td>
      <td>4500</td>
      <td>https://i.ytimg.com/vi/s9FH4rDMvds/default.jpg</td>
      <td>False</td>
      <td>False</td>
      <td>Salve rapaziada, neste vídeo me declarei pra e...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>jbGRowa5tIk</td>
      <td>ITZY “Not Shy” M/V TEASER</td>
      <td>2020-08-11T15:00:13Z</td>
      <td>UCaO6TYtlC8U5ttz62hTrZgg</td>
      <td>JYP Entertainment</td>
      <td>10</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>JYP Entertainment|JYP|ITZY|있지|ITZY Video|ITZY ...</td>
      <td>6000070</td>
      <td>714310</td>
      <td>15176</td>
      <td>31040</td>
      <td>https://i.ytimg.com/vi/jbGRowa5tIk/default.jpg</td>
      <td>False</td>
      <td>False</td>
      <td>ITZY Not Shy M/V[ITZY Official] https://www.yo...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3EfkCrXKZNs</td>
      <td>Oh Juliana PARÓDIA - MC Niack</td>
      <td>2020-08-10T14:59:00Z</td>
      <td>UCoXZmVma073v5G1cW82UKkA</td>
      <td>As Irmãs Mota</td>
      <td>22</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>OH JULIANA PARÓDIA|MC Niack PARÓDIA|PARÓDIAS|A...</td>
      <td>2296748</td>
      <td>39761</td>
      <td>5484</td>
      <td>0</td>
      <td>https://i.ytimg.com/vi/3EfkCrXKZNs/default.jpg</td>
      <td>True</td>
      <td>False</td>
      <td>Se inscrevam meus amores! 📬 Quer nos mandar al...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>gBjox7vn3-g</td>
      <td>Contos de Runeterra: Targon | A Estrada Tortuosa</td>
      <td>2020-08-11T15:00:09Z</td>
      <td>UC6Xqz2pm50gDCORYztqhDpg</td>
      <td>League of Legends BR</td>
      <td>20</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>Riot|Riot Games|League of Legends|lol|trailer|...</td>
      <td>300510</td>
      <td>46222</td>
      <td>242</td>
      <td>2748</td>
      <td>https://i.ytimg.com/vi/gBjox7vn3-g/default.jpg</td>
      <td>False</td>
      <td>False</td>
      <td>Você se unirá aos Lunari e aos Solari em Targo...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>npoUGx7UW7o</td>
      <td>Entrevista com Thammy Miranda | The Noite (10/...</td>
      <td>2020-08-11T20:04:02Z</td>
      <td>UCEWOoncsrmirqnFqxer9lmA</td>
      <td>The Noite com Danilo Gentili</td>
      <td>23</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>The Noite|The Noite com Danilo Gentili|Danilo ...</td>
      <td>327235</td>
      <td>22059</td>
      <td>3972</td>
      <td>2751</td>
      <td>https://i.ytimg.com/vi/npoUGx7UW7o/default.jpg</td>
      <td>False</td>
      <td>False</td>
      <td>Danilo Gentili recebe Thammy Miranda. Após pas...</td>
    </tr>
  </tbody>
</table>
</div>


## 3. Exploratory Data Analysis

The first Step of the project is to perform some exploratory analysis to get some visual insights from that could be useful for the final Solution

### 1. Likes Per Views and Comments Per Views

The first Insight extracted from the data for most of the categories is that it’s more likely to have more comments when the rating are enabled for the video, and it’s ideal to leave aslo the comment enabled to get more likes

 ![image](https://user-images.githubusercontent.com/103480107/202587482-c7ee2d87-aeec-41c2-8291-2fa5e1e4daed.png)
 
 ### 2. Publication’s  day of the week

The first Insight extracted from the data for most of the categories is that it’s more likely to have more comments when the rating are enabled for the video, and it’s ideal to leave aslo the comment enabled to get more like

![image](https://user-images.githubusercontent.com/103480107/202584869-ece55f2f-c6d8-40bf-bad4-6a3f17c435bb.png)

 ### 3. Time To reach Trending

It’s Visualy observed that time taken for a video te reach trending  varies between the different categories and Countries, that could be useful for the investors to not invest on videos published for a longer time than the Duration it usualy take videos for similar videos to reach trending

![image](https://user-images.githubusercontent.com/103480107/202585091-69168112-3f70-41bc-84db-71d35bac2bbd.png)

 ### 4.  Word Cloud Tags
 
 THE Tags world cloud could be very useful to extract the most used tags in the trending videos and that could be used by youtubers.
 
 ![image](https://user-images.githubusercontent.com/103480107/202585257-73e7f271-3a7b-4090-99e7-8ab187aa347a.png)
 
  ## 4. Solution Presentation
 
 The Final conclusion of the project is framed as an interactive guides for youtubers and Investors based on the insights found in the previous part

### Youtubers guide

<p>Concerning the Investors&nbsp;:</p><ol><li>the Guide start by showing an evaluation of the for the different categories in term of duration in tranding to help them to chose&nbsp;categries where the videos could stay in trending for longer periods <br></li><li>&nbsp;After Chosing a specific categorie the most optimal days of the week to publish their videos are displayed</li><li>Finally the word cloud&nbsp;provide the best Tags to use for a specific country and a specific categorie .</li></ol> 

![image](https://user-images.githubusercontent.com/103480107/202586701-422b8cf1-6a66-4f47-bb1f-5e5c38288547.png)
![image](https://user-images.githubusercontent.com/103480107/202586711-908cf159-f598-45df-8208-36e68eab68d7.png)


### Invesors Guide

<p>Concerning the Investors&nbsp;:</p><ol><li>1.the Guide start by showing an evaluation of the reach for the different categories in the targeted country or countries to help them decide ,</li><li>2.After Chosing a specific categorie the visual time taken to reach trending define the limit for the duration online</li><li>3.Finally the best chanels with the highest number of trending videos are displayed in order to help the investor decide which chanel to invest in on the chosen countries</li></ol>  

![image](https://user-images.githubusercontent.com/103480107/202586231-4caca9df-9482-4808-9935-005d0b7cf987.png)


## 4. Usability 

  - Clone the [repo](https://github.com/amine-abdollah/Youtube_Trending_Videos_Analysis) using this command in your terminal `git clone 
