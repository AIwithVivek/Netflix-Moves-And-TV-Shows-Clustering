<h1 align="center"> Netflix Movies and TV Shows Clustering</h1>

<p align="center"> 
<img src="https://media1.tenor.com/m/NerN41mjgV0AAAAC/netflix-intro.gif" alt="..." height="500px">
</p>

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


<table style="width: 100%; text-align: center; border-collapse: collapse;">
    <tr>
        <td style="padding: 10px; background-color: #333;">
            <a href="https://github.com/AIwithVivek/Netflix-Movies-and-TV-shows-Clustering#1-introduction" style="color: red; text-decoration: none;">Introduction</a>
        </td>
        <td style="padding: 10px; background-color: #333;">
            <a href="https://github.com/AIwithVivek/Netflix-Movies-and-TV-shows-Clustering#2-eda-summary" style="color: red; text-decoration: none;">EDA Summary</a>
        </td>
    </tr>
    <tr>
        <td style="padding: 10px; background-color: #333;">
            <a href="https://github.com/AIwithVivek/Netflix-Movies-and-TV-shows-Clustering#3-clustering-summary" style="color: red; text-decoration: none;">Clustering Summary</a>
        </td>
        <td style="padding: 10px; background-color: #333;">
            <a href="https://github.com/AIwithVivek/Netflix-Movies-and-TV-shows-Clustering#4-content-based-recommender-system-using-cosine-similarity" style="color: red; text-decoration: none;">Content Based Recommender System</a>
        </td>
    </tr>
    <tr>
        <td style="padding: 10px; background-color: #333;" colspan="2">
            <a href="https://github.com/AIwithVivek/Netflix-Movies-and-TV-shows-Clustering#5-conclusions" style="color: red; text-decoration: none;">Conclusions</a>
        </td>
    </tr>
</table>


![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 1. Introduction:
a) Netflix, based in California, is a leading subscription-based streaming service and production company. As reported by Statista, Netflix had around 220.67 million paid subscribers globally by the second quarter of 2022. To enhance the overall user experience, it is essential for Netflix to effectively categorize the shows available on its platform.

b) By implementing clustering techniques, we can identify shows that are similar and different from one another. These clusters can be used to provide users with personalized recommendations based on their individual preferences.

c) The objective of this project is to categorize Netflix shows into distinct groups, where shows within the same cluster share similarities, while those in different clusters are noticeably different from each other.

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


## 2. EDA Summary:

* The dataset contains more movies (69.14%) compared to TV shows (30.86%).
* Raul Campos and Jan Suter have jointly directed 18 films and shows, the highest by any director in the dataset.
* The majority of films and shows are produced in the US, followed by India and the UK. These top three countries account for approximately 56% of the content, and this figure rises to 78% when considering the top 10 countries.
* Netflix has a larger collection of newer content than older movies and shows.
* Drama is the leading genre, followed by comedy and documentary, collectively accounting for around 41% of the content. The share increases to 82% when considering the top 10 genres.
* October, November, December, and January see the highest average number of shows added.
* In 2020, there was a decline in the number of new shows, likely due to production halts caused by the COVID-19 pandemic. The dataset includes Netflix data until January 16, 2021, explaining the lower count for that year.
* Most Netflix content is targeted at an adult and young adult audience.
* Over time, Netflix has steadily expanded its library. Although the number of movies added in 2020 declined, TV shows did not follow the same trend, possibly indicating a shift in focus toward series.
* While some TV series in the dataset have up to 16 seasons, most have only one season, suggesting that many are recent releases with more seasons likely in the future. Very few shows have over 8 seasons.
* Movie durations range from 3 minutes to 312 minutes, with a near-normal distribution.
* Netflix offers films dating as far back as 1942. Films from the 1940s tend to have shorter runtimes on average, while movies made in the 1960s have the longest durations. The average runtime has been gradually declining since the 2000s.
* Dramas, comedies, and documentaries are the top genres for movies, while international, crime, and kids' content dominate TV shows on Netflix.
* Raul Campos and Jan Suter have directed the most movies, followed by Marcus Roboy, Jay Karas, and Cathy Garcia-Molina. Alastair Fothergill holds the record for directing the most TV shows (three), with only six directors having worked on more than one series.
* Samuel West has appeared in 10 movies, followed by Jeff Dunham with 7. David Attenborough leads the TV show category with 13 appearances, trailed by Michela Luci, Jamie Watson, Anna Claire Bartlam, Dante Zee, and Eric Peterson, each with four appearances.

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


## 3. Clustering Summary:
* Clusters were created based on features such as Director, Cast, Country, Rating, Genre (Listed in), and Description.
* Preprocessing steps included: tokenizing the text, removing non-ASCII characters, converting text to lowercase, eliminating punctuation, converting numbers to their word equivalents, and applying stemming and lemmatization.
* The text corpus was vectorized using the TF-IDF vectorizer, generating 20,000 features.
* To manage dimensionality, the top 4,000 components were retained as they captured over 80% of the variance in the dataset.

### 3.1. K-Means Clustering:
* The optimal number of clusters was determined using the elbow method and Silhouette score.
* The highest Silhouette score was achieved with 6 clusters using the K-means algorithm.
* The Silhouette score for 6 clusters was 0.0082.

### 3.2. Hierarchical Clustering:
* Agglomerative clustering was used to form clusters, with the dendrogram helping determine the optimal number of clusters.
* Based on the dendrogram, 12 clusters were identified at a Euclidean distance of 3.8 units.
* Clustering approach: Agglomerative clustering
* Distance metric: Euclidean
* Linkage method: Ward

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


## 4. Content-Based Recommender System Using Cosine Similarity:
* A straightforward content-based recommender system can be developed by identifying the similarity between shows.
* If a user has watched a show on Netflix, the system should recommend a list of similar shows based on their preferences. Cosine similarity can be used to calculate the similarity score between shows.
* The similarity between two vectors (A and B) is determined by taking their dot product and dividing it by the product of their magnitudes. Essentially, the cosine similarity score increases as the angle between the vectors decreases.

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 5. Conclusions:
* This project addressed a text clustering challenge where the goal was to group Netflix shows into clusters based on their similarities, ensuring that shows in the same cluster are alike while those in different clusters are distinct.
* The dataset comprised approximately 7,787 records and 11 features.
* It was observed that Netflix has more movies than TV shows, and the number of shows on the platform is growing rapidly. Additionally, most of the shows originate from the United States, and the majority are aimed at adult and young adult audiences.
* Clustering was based on attributes such as director, cast, country, genre, and description. The data from these fields was preprocessed, tokenized, and vectorized using a TF-IDF vectorizer, generating a total of 20,000 features.
* Principal Component Analysis (PCA) was applied to manage dimensionality, with 4,000 components capturing over 80% of the variance. As a result, the number of components was limited to 4,000.
* The k-means clustering algorithm was initially used, and the optimal number of clusters was determined to be 6 based on the elbow method and Silhouette score.
* A hierarchical clustering model was then created using the Agglomerative Clustering algorithm, and 12 clusters were identified by analyzing the dendrogram.
* Lastly, a content-based recommender system was developed using cosine similarity to generate a similarity matrix. This system is capable of making 10 personalized recommendations based on the type of show a user has previously watched.
