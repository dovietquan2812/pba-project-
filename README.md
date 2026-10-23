# Research Proposal

## Do Delivery Delays or Higher Shipping Costs Matter More? Evidence from Brazilian E-Commerce

**Long Tran The, Quan Do Viet, Hoang Nguyen Duc**
October 22, 2026

---

## 1. Research Question

**Research Question:** How are delivery delays and higher shipping fees related to customer satisfaction in Brazilian e-commerce, and is one of them more positively/negatively associated with negative customer reviews?

The research question is associational (descriptive) rather than causal. This study aims to describe and explore the possible relationships between delivery performance and costs, and customer satisfaction.

The findings will allow online businesses to better understand what aspects of delivery they should focus on to provide a positive customer experience and, consequently, obtain positive feedback.

## 2. Hypotheses and Rationale

The study will pursue three hypotheses:

**H1:** Orders that were delivered after the expected delivery date are more likely to incur negative reviews.

Customers who purchase online set their expectations based on the promised delivery time of the seller. When this date is exceeded, the customer may feel upset that they will have to wait longer for the product than expected. Therefore, it stands to reason to assume that negative customer reviews will be more common for late deliveries compared to on-time deliveries.

**H2:** Higher freight costs relative to the value of items purchased are associated with negative reviews.

When purchasing an item online, the buyer will consider the price in relation to the freight costs. For instance, when the delivered price significantly exceeds the value of an item, a customer may feel like they have to pay much more for something relatively cheap. Hence, it is reasonable to assume that a customer will be more inclined to provide a negative review when the shipping fee is high.

**H3:** Delivery delays are more positively/negatively associated with negative customer reviews than shipping costs.

As mentioned above, customers who purchase online will set their expectations in relation to the delivery date and cost of the item. While the latter depends entirely on the buyer, the former is jointly determined by the seller and the courier. Therefore, the experience of the customer will be impacted more significantly by late delivery than the increase in freight costs. Even if the customer was aware of the price before purchasing, the late delivery will still disappoint them since the courier did not meet the seller's expectations.

## 3. Data Description

### 3.1 Source and Collection

The data used for this study has been provided by Olist in the form of the Brazilian E-Commerce Public Dataset available on Kaggle. It includes more than 100,000 orders, made by customers on Olist's e-commerce marketplace in 2016–2018. This dataset has been collected by Olist in the course of its business activities and includes the company's past commercial transactions. The customer's order details, product prices, freight costs, delivery dates, and reviews have also been included. The latter were obtained by Olist upon the customer's request after the delivery of their orders.

The study's analysis will incorporate three CSV files:

- `olist_orders_dataset.csv` – order status, purchase and delivery dates (estimated and actual).
- `olist_order_items_dataset.csv` – product prices and freight costs for individual items.
- `olist_order_reviews_dataset.csv` – customer satisfaction scores (1–5).

### 3.2 Unit of Observation and Sample

The unit of observation for this study is an individual customer order. Each row represents an entity with an individual order ID.

The original size of the sample is 100,000 customer orders for the period between 2016–2018. The data will be used in the analysis as provided, focusing on delivered orders with review scores and delivery dates. The exact number of units for analysis will be identified in the course of the exploration of the data.

As one order may include several items, the item-wise price and freight costs will be aggregated at the order level. Similarly, the number of customer reviews per order will be examined to ensure that one order is not included in the sample multiple times (if a customer provided multiple reviews).

### 3.3 Variables

| Variable | Meaning | Unit |
|---|---|---|
| `review_score` | Customer satisfaction score | 1–5 stars |
| `low_rating` | Negative customer review | 1–2 stars |
| `late_delivery` | Delivery was late | Binary |
| `delay_days` | Number of days passed after the expected delivery date | Days |
| `freight_value` | Shipping costs for the order | BRL |
| `product_value` | Price of goods in the order | BRL |
| `freight_ratio` | Ratio between freight costs and price of goods | Ratio |
| `delivery_time` | Duration between the date of purchase and actual delivery | Days |
| `item_count` | Quantity of items in the order | Count |
| `purchase_month` | Month of purchase | Month |

## 4. Key Variables and Proposed Analysis

The main outcome variable of this study will be `low_rating` (1 – negative customer review; 0 – positive review). The key independent variables will be delivery performance and freight costs. The former will be identified as delivery late vs. on time and will be classified as `late_delivery = 1` if the actual delivery date exceeds the expected one and `late_delivery = 0` otherwise.

Freight costs will be expressed as the freight value divided by product value ratio:

$$
\text{freight\_ratio} = \frac{\text{freight\_value}}{\text{product\_value}}
$$

The following analyses will be conducted. First, descriptive statistics and graphs will be produced to compare the negative review rates across delivery status and freight cost categories. Then, to further explore the relationships between the variables and determine whether they are statistically significant, regression analysis will be conducted.

It will be examined how the independent variables associate with the dependent variable while controlling for other characteristics. Instead of comparing the magnitude of coefficients (which is not possible since the variables are measured on different scales), the study will document the estimated difference in the likelihood of a negative review when comparing the different levels of a certain independent variable.

For instance, it will be assessed how many times more likely it is that an order will receive a negative review if delivery happens late compared to on-time. Similarly, the analysis will examine how much a change in the freight ratio (x%) impacts the log-odds of negative customer reviews.

## 5. Expected Evidence and Interpretation

**Evidence supporting H1:** Delivered late orders have a higher rate of negative reviews compared to on-time deliveries. A positive link between late delivery and negative reviews is identified after controlling for other order characteristics.

**Evidence contradicting H1:** Negative review rates for late deliveries are comparable to those for on-time deliveries. Moreover, the association between late delivery and negative reviews disappears after controlling for other order characteristics.

**Evidence supporting H2:** The higher the freight ratio, the higher is the likelihood that an order will be reviewed negatively, including after controlling for other order characteristics.

**Evidence contradicting H2:** There is no positive association between increases in freight ratio and negative customer reviews, or a negative association between the freight ratio and negative reviews.

**Evidence supporting H3:** The delivery delay is positively associated with the estimated probability of a negative review at a higher rate compared to the impact of a unit change in freight ratio on the same parameter.

**Evidence contradicting H3:** Higher freight costs are more strongly associated with negative reviews than are late deliveries. However, the differences in the impact of the two variables on the dependent variable are not consistent enough to establish a clear ranking.

The study will provide evidence in support of businesses' decisions to focus on providing fast delivery rather than keeping freight costs low in the pursuit of customer satisfaction. However, the results will need to be interpreted as indicative of statistical associations rather than causal relationships. Other factors, such as product quality, seller reputation, and customer expectations, may also affect negative review rates.

---

**Data source:** Olist. (n.d.). *Brazilian E-Commerce Public Dataset by Olist*. Kaggle. Web.