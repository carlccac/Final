# Analysis of 2020 Congressional PAC Donations by State

An exploratory analysis of Political Action Committee donations was conducted for the 2020 PA congressional election. As would be expected, most candidates' donations were a small percentage of their total donations; that is, the number of candidates declines as the percentage of PAC donations increases. However, a histogram of the percentage of PAC donations for PA revealed a curious uptick; as the percentage of PAC donations increased over 45%, so did the number of candidates. This would indicate a large amount of PAC influence in the PA elections and warrants extending the analysis to all 50 states. 

![alt text](https://github.com/carlccac/Final/blob/main/pa_hist.png)

As with the original PA study, data was gathered from Propublica.org using their API (Application Programmer Interface) and python. A list of candidates for each state was acquired. Then, financial data for each candidate was gathered; namely, their total donations and their PAC donations, again using the Propublica API.

A list of 3558 candidates was compiled. There are currently 435 congressional districts and the winners were determined using Wikipedia's list of current members for each district. Python was used to scrape the wikipedia page and match up the winners from the Propublica data.

Python's Pandas was used to analyze the data. All candidates who were not either Republicans or Democrats were removed from the data set. All candidates with no donations were also removed. PAC donations as a percentage of total donations were calculated for each candidate. PAC donations greater than 45% of total donations was used as an indicator of excessive PAC influence as this appeared to be the point on the PA histogram where the uptick started. Therefore, if a candidate had PAC donations greater than 45% of their total donations this was noted.   

Finally, a table was created that listed the number of candidates per state, the number of candidates whose PAC donations were greater than 45% who won and the number of candidates whose PAC donations were greater than 45% who lost. The data is visualized in a stacked bar chart; blue bars are winners, orange bars are those who lost. The chart is sorted by number of winning candidates whose donations exceeded 45%.

![alt text](https://github.com/carlccac/Final/blob/main/final_stack_bar.svg)

As can be seen from the chart, excessive PAC spending is highly correlated with winning elections. Surprisingly, PAC influence seems to be inversely correlated with the number of candidates and would suggest that PAC influence is greater in smaller states. This can be seen in the following plot where the number of candidates whose PAC donations exceed 45% is plotted against number of total candidates.

![alt text](https://github.com/carlccac/Final/blob/main/final_scatter.svg)

# Future Research:

Future research could extend the study by adding demographic data for each district. This would allow further analysis by weighting the results as per the demographic data, i.e., population, population density, income, etc.

# Data Wrangling, Cleaning and Analysis:

https://github.com/carlccac/Final/blob/main/data_wrangle_clean.ipynb

https://github.com/carlccac/Final/blob/main/analysis_final.ipynb

# Summary statistics for the '>45% as % of total' column are as follows:

count     50.000000

mean      17.792200

std       16.551416

min        0.000000

25%        8.587500

50%       13.735000

75%       23.555000

max      100.000000


# Table of data used in analysis

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>st</th>
      <th>#cans</th>
      <th>&gt;45% wins</th>
      <th>&gt;45% lost</th>
      <th>&gt;45% as % of total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>CA</td>
      <td>212</td>
      <td>24</td>
      <td>5</td>
      <td>13.68</td>
    </tr>
    <tr>
      <th>42</th>
      <td>TX</td>
      <td>226</td>
      <td>18</td>
      <td>7</td>
      <td>11.06</td>
    </tr>
    <tr>
      <th>34</th>
      <td>OH</td>
      <td>48</td>
      <td>11</td>
      <td>3</td>
      <td>29.17</td>
    </tr>
    <tr>
      <th>8</th>
      <td>FL</td>
      <td>152</td>
      <td>11</td>
      <td>2</td>
      <td>8.55</td>
    </tr>
    <tr>
      <th>37</th>
      <td>PA</td>
      <td>53</td>
      <td>10</td>
      <td>0</td>
      <td>18.87</td>
    </tr>
    <tr>
      <th>13</th>
      <td>IL</td>
      <td>66</td>
      <td>9</td>
      <td>2</td>
      <td>16.67</td>
    </tr>
    <tr>
      <th>33</th>
      <td>NY</td>
      <td>131</td>
      <td>8</td>
      <td>3</td>
      <td>8.40</td>
    </tr>
    <tr>
      <th>9</th>
      <td>GA</td>
      <td>86</td>
      <td>7</td>
      <td>1</td>
      <td>9.30</td>
    </tr>
    <tr>
      <th>14</th>
      <td>IN</td>
      <td>45</td>
      <td>6</td>
      <td>1</td>
      <td>15.56</td>
    </tr>
    <tr>
      <th>30</th>
      <td>NJ</td>
      <td>57</td>
      <td>6</td>
      <td>0</td>
      <td>10.53</td>
    </tr>
    <tr>
      <th>26</th>
      <td>NC</td>
      <td>79</td>
      <td>6</td>
      <td>1</td>
      <td>8.86</td>
    </tr>
    <tr>
      <th>23</th>
      <td>MO</td>
      <td>25</td>
      <td>5</td>
      <td>1</td>
      <td>24.00</td>
    </tr>
    <tr>
      <th>16</th>
      <td>KY</td>
      <td>17</td>
      <td>5</td>
      <td>0</td>
      <td>29.41</td>
    </tr>
    <tr>
      <th>21</th>
      <td>MI</td>
      <td>61</td>
      <td>5</td>
      <td>2</td>
      <td>11.48</td>
    </tr>
    <tr>
      <th>46</th>
      <td>WA</td>
      <td>41</td>
      <td>5</td>
      <td>1</td>
      <td>14.63</td>
    </tr>
    <tr>
      <th>5</th>
      <td>CO</td>
      <td>20</td>
      <td>4</td>
      <td>1</td>
      <td>25.00</td>
    </tr>
    <tr>
      <th>18</th>
      <td>MA</td>
      <td>38</td>
      <td>4</td>
      <td>0</td>
      <td>10.53</td>
    </tr>
    <tr>
      <th>2</th>
      <td>AR</td>
      <td>8</td>
      <td>4</td>
      <td>0</td>
      <td>50.00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AL</td>
      <td>27</td>
      <td>4</td>
      <td>1</td>
      <td>18.52</td>
    </tr>
    <tr>
      <th>35</th>
      <td>OK</td>
      <td>21</td>
      <td>3</td>
      <td>0</td>
      <td>14.29</td>
    </tr>
    <tr>
      <th>19</th>
      <td>MD</td>
      <td>46</td>
      <td>3</td>
      <td>1</td>
      <td>8.70</td>
    </tr>
    <tr>
      <th>36</th>
      <td>OR</td>
      <td>32</td>
      <td>3</td>
      <td>1</td>
      <td>12.50</td>
    </tr>
    <tr>
      <th>39</th>
      <td>SC</td>
      <td>22</td>
      <td>3</td>
      <td>0</td>
      <td>13.64</td>
    </tr>
    <tr>
      <th>24</th>
      <td>MS</td>
      <td>11</td>
      <td>3</td>
      <td>0</td>
      <td>27.27</td>
    </tr>
    <tr>
      <th>44</th>
      <td>VA</td>
      <td>48</td>
      <td>3</td>
      <td>1</td>
      <td>8.33</td>
    </tr>
    <tr>
      <th>6</th>
      <td>CT</td>
      <td>16</td>
      <td>3</td>
      <td>0</td>
      <td>18.75</td>
    </tr>
    <tr>
      <th>47</th>
      <td>WI</td>
      <td>29</td>
      <td>2</td>
      <td>2</td>
      <td>13.79</td>
    </tr>
    <tr>
      <th>41</th>
      <td>TN</td>
      <td>34</td>
      <td>2</td>
      <td>0</td>
      <td>5.88</td>
    </tr>
    <tr>
      <th>43</th>
      <td>UT</td>
      <td>29</td>
      <td>2</td>
      <td>0</td>
      <td>6.90</td>
    </tr>
    <tr>
      <th>12</th>
      <td>ID</td>
      <td>5</td>
      <td>2</td>
      <td>0</td>
      <td>40.00</td>
    </tr>
    <tr>
      <th>48</th>
      <td>WV</td>
      <td>9</td>
      <td>2</td>
      <td>0</td>
      <td>22.22</td>
    </tr>
    <tr>
      <th>32</th>
      <td>NV</td>
      <td>25</td>
      <td>2</td>
      <td>0</td>
      <td>8.00</td>
    </tr>
    <tr>
      <th>28</th>
      <td>NE</td>
      <td>11</td>
      <td>2</td>
      <td>0</td>
      <td>18.18</td>
    </tr>
    <tr>
      <th>22</th>
      <td>MN</td>
      <td>24</td>
      <td>1</td>
      <td>1</td>
      <td>8.33</td>
    </tr>
    <tr>
      <th>15</th>
      <td>KS</td>
      <td>17</td>
      <td>1</td>
      <td>0</td>
      <td>5.88</td>
    </tr>
    <tr>
      <th>0</th>
      <td>AK</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>100.00</td>
    </tr>
    <tr>
      <th>10</th>
      <td>HI</td>
      <td>8</td>
      <td>1</td>
      <td>0</td>
      <td>12.50</td>
    </tr>
    <tr>
      <th>27</th>
      <td>ND</td>
      <td>2</td>
      <td>1</td>
      <td>0</td>
      <td>50.00</td>
    </tr>
    <tr>
      <th>17</th>
      <td>LA</td>
      <td>19</td>
      <td>1</td>
      <td>2</td>
      <td>15.79</td>
    </tr>
    <tr>
      <th>20</th>
      <td>ME</td>
      <td>6</td>
      <td>1</td>
      <td>0</td>
      <td>16.67</td>
    </tr>
    <tr>
      <th>49</th>
      <td>WY</td>
      <td>4</td>
      <td>1</td>
      <td>0</td>
      <td>25.00</td>
    </tr>
    <tr>
      <th>38</th>
      <td>RI</td>
      <td>4</td>
      <td>1</td>
      <td>0</td>
      <td>25.00</td>
    </tr>
    <tr>
      <th>45</th>
      <td>VT</td>
      <td>3</td>
      <td>1</td>
      <td>0</td>
      <td>33.33</td>
    </tr>
    <tr>
      <th>7</th>
      <td>DE</td>
      <td>3</td>
      <td>1</td>
      <td>0</td>
      <td>33.33</td>
    </tr>
    <tr>
      <th>25</th>
      <td>MT</td>
      <td>9</td>
      <td>0</td>
      <td>1</td>
      <td>11.11</td>
    </tr>
    <tr>
      <th>29</th>
      <td>NH</td>
      <td>7</td>
      <td>0</td>
      <td>0</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>31</th>
      <td>NM</td>
      <td>21</td>
      <td>0</td>
      <td>0</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>AZ</td>
      <td>40</td>
      <td>0</td>
      <td>0</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>11</th>
      <td>IA</td>
      <td>19</td>
      <td>0</td>
      <td>0</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>40</th>
      <td>SD</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>0.00</td>
    </tr>
  </tbody>
</table>
