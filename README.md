Download Link: https://assignmentchef.com/product/solved-dsl-lab9-build-a-regression-model-to-identify-the-price-of-an-airbnb-apartment
<br>
The main objective of this laboratory is to put into practice what you have learned on regression techniques. You will work on a tabular dataset. In particular, you will try to build a regression model that is able to identify the price of an Airbnb apartment, given different information related to the listing.

<strong>Important note. </strong>For what concerns this laboratory, you are encouraged to upload your results to the competition we launched on our platform, even if the submission will not count on your final exam mark. You have to use the same personal key you already used for Lab 5. If you do not have a key yet, please write to <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="5b3c322e283e2b2b3e753a2f2f3a353a2832341b2b3437322f3475322f75">[email protected]</a> Refer to Section 3 to read more about the competition.

<h1>1          Preliminary steps</h1>

<h2>1.1         Datasets</h2>

In this laboratory, you will use a publicly available dataset. Public Domain Dedication datasets constitute an extremely valuable asset for the data science community. If you want to know more about how they are distributed, refer to the <a href="https://creativecommons.org/publicdomain/zero/1.0/">CC0 licence</a><a href="https://creativecommons.org/publicdomain/zero/1.0/">.</a>

<h3>1.1.1         New York City Airbnb Open Data</h3>

This public dataset is part of Airbnb, and the original source can be found on <a href="http://insideairbnb.com/">Inside Airbnb</a><a href="http://insideairbnb.com/">.</a>

Each row of the dataset corresponds to an Airbnb listing in New York City, for the year 2019. As for the previous competition, the dataset has been divided in a Development set and an Evaluation one. You will find more about them later in the document.

Each file has an initial header line, containing the names of attributes at your disposal:

<ul>

 <li>id: a unique identifier of the listing</li>

 <li>name</li>

 <li>host_id: a unique identifier of the host</li>

 <li>host_name</li>

 <li>neighborhood_group: neighborhood location in the city</li>

 <li>neighborhood: name of the neighborhood</li>

 <li>latitude: coordinate expressed as floating point number</li>

 <li>longitude: coordinate expressed as floating point number</li>

 <li>room_type</li>

 <li>price: price per night expressed in dollars</li>

 <li>minimum_nights: minimum nights requested by the host</li>

 <li>number_of_reviews</li>

 <li>last_review: date of the last review expressed as YYYY-MM-DD</li>

 <li>reviews_per_month: average number of reviews per month</li>

 <li>calculated_host_listings_count: amount of listing of the host</li>

 <li>availability_365: number of days when the listing is available for booking You can download the dataset at: https://github.com/dbdmg/data-science-lab/raw/master/datasets/NYC_Airbnb.zip</li>

</ul>

<h3>1.1.2         Dataset tree hierarchy</h3>

The data have been distributed uniformly in two separate collections. Each collection is in a different file. The dataset archive is organized as follows:

<ul>

 <li>csv (Development set): a collection of listings <strong>with </strong>the price column. This collection of data has to be used during the development of the regression model.</li>

 <li>csv (Evaluation set): a collection of listings <strong>without </strong>the price column. This collection of data has to be used to produce the submission file.</li>

 <li>csv: a sample submission file.</li>

</ul>

So far, you should be used to work, while developing your models, with training, validation and test sets. In this case, the Development data must be used to tune your hyper-parameters while you should consider the Evaluation portion as the actual test set.

<h1>2          Exercises</h1>

In this laboratory, you have a single regression task to carry out.

<h2>2.1         NYC Airbnb listing price regression</h2>

In this exercise, you will try to predict the price of an Airbnb listing in NYC, published in 2019, using several contextual information. To do so, your primary goal will be modeling, through a regression-based pipeline, the relationship between information on the listing (e.g. its geographical location, the reviews it received, or many other metrics you might figure out) and the price itself.

Once your model is complete, you will predict, for a set of listings whose price is unknown, how much would it cost to you spending one night at them.

Finally, you will be able to upload your regression results and participate to the lab competition.

<ol>

 <li>Load the dataset from the root folder.</li>

 <li>Focus now on the data preparation step. You should have noticed that the attributes that describe each listing are heterogeneous, both on the source (e.g. geographical, related to host, related to Airbnb, etc.) and on the type (e.g. numerical, categorical, date, etc.). Before continuing, take you your time to answer these questions:

  <ul>

   <li>which attribute (or set of attributes) you think could drive the price per night the most?</li>

   <li>can you detect any irregularity in any attribute distribution?</li>

   <li>if your regression model will fit on numerical data only, how could you handle categorical attributes?</li>

  </ul></li>

</ol>

Transform your initial dataset following the ideas you draw out.

<ol start="3">

 <li>Once you have your final dataset representation, choose one regression model of those you know. Then, perform the classic training-validation pipeline on the Development dataset to identify the best set of hyper-parameters for your model. As you can read in Section 3, we will evaluate your results on the <em>R</em><sup>2 </sup>score (or <a href="https://en.wikipedia.org/wiki/Coefficient_of_determination">Coefficient of determination</a><a href="https://en.wikipedia.org/wiki/Coefficient_of_determination">)</a>. Hence, it is a reasonable option trying to optimize it on the Development set.</li>

 <li>Assign a price value to each listing in the Evaluation set.</li>

 <li>Define a function to generate a 2D scatterplot with the prices. The chart must be drawn as heatmap: use the latitude and longitude coordinates along the axes and the price value to assign a color to the point. Then, apply the function to the prices from the Development set and to the ones you predicted for the Evaluation set. From Section 1, you know that Development and Evaluation were generated with a uniform sampling on the initial listings. So, what should you expect on the map, if your regression were correct?</li>

 <li>Upload your results to the submission platform. Head to Section 3 to know more about it.</li>

 <li>Compile your final report and upload it to the “Portale della Didattica” as described in section 2.</li>

</ol>


