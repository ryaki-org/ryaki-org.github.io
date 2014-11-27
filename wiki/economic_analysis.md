**Definition 1**

* Let \\(c_i \in C\\) be the credit sources.
* Let \\(b_i \in P\\) be the producers.
* Let \\(i_{ci} \in I_c\\) be the capital investors, members or ryaki that have invested in investment units.
* Let \\(i_{pi} \in I_p\\) be the members or ryaki that have loaned producers.

* Let \\(n_i \in N\\) be the number of investors at credit source \\(c_i\\).
* Let \\(I_{ei}\\) the investment equation percentage for credit source \\(c_i\\).
* Let \\(V_{ei}\\) the value equation percentage for production unit \\(P_ui\\).
* Let \\(P_{ui}\\) be the profit equation of credit source \\(c_i\\).
* Let \\(p_i \in P\\) be the production rate of credit source \\(c_i\\).
* Let \\(p_{ri} \in P_r\\) be the price of the product of credit source \\(c_i\\) expressed in ryaki currency.
* Let \\(e_i \in E\\) be the purchase rate of credit source \\(c_i\\) expressed in ryaki currency.

**Lemma 1**

$$e_i <  p_ip_{ri}$$

**Investor Exchange rate** 

The investor rate of return \\(i_{rri}\\) is equal to:

Cases:

* Investment unit
$$ i_{rri} = e_iI_{ei}$$

* Producer
$$ i_{rri} = e_j(1-I_{ej})V_{ei} $$




**Definition 2**

We call \\(r_{ci} = \frac{i_{rri}}{n_i}\\) the current average rate of return per investor for credit source \\(c_i\\).


**Lemma 2**

Let \\(m_{ij}\\) the amounts of credit that investors \\(i\\) have on credit source \\(c_i\\) in increasing order of quantity.
Then the average rate of return per investor for \\(m_{ij-1}< m < m_{ij}\\) credit is given by this equation:
$$R_i:R \rightarrow R$$
$$R_i(m) = \frac{m}{\sum_{l=1}^{j-1}\frac{(n_i-l-1)(m_{il}-m_{il-1})}{i_{eri}} + 
 \frac{(n_i-j-1)(m-m_{ij-1})}{i_{eri}}}$$  where \\(m_0=0\\).



*comment 1:* The above average rate is so, because we use the fair queue algorithm.

**Definition 3**

* We call \\(R_{e}\\) the rate of return from purchases of products with money.
    * We call \\(R_{ee}\\) the rate of return when the purchasors are not ryaki members.
* We call \\(R_{r}\\) the rate of return from purchases with ryaki credit.

**Lemma 3**

Let's assume that:

* \\(R_{ej}\\) is the external rate of return of credit sources \\(c_j\\) at credit \\(0_+\\) if one more investor joins them.
* there is connectivity of unlimited value from any investment to another except investment unit \\(c\\)

and for the investment unit \\(c\\) and their product,

* \\(R_{v}\\) is the purchase rate of that pruduct by the internal network if there was connectivity
* \\(p_{v}\\) is the percentage of that purchase rate that would be done with money if there was no way to use the ryaki network. 

If we assume that 

* both types of consumers have equal chance to use ryaki.

Then the optimal way for an investor that has credit in credit source \\(c\\) to maximize his rate of return is to open trust links of minimum limit with \\(m\\) credit sources such that:
$$R_v\approx \sum_{j=1}^{m}R_{ej}$$
Then his internal rate of return is:

if
$$R_v > \sum_{j=1}^{m}R_{ej}$$
then
$$R_{er} = max(\sum_{j=1}^{m}R_{ej},R_vp_v)$$
if
$$R_v < \sum_{j=1}^{m}R_{ej}$$
then
$$R_{er} = R_v$$

*proof:* If \\(p_{v}<1\\), there are customers that do not have money, they have credit and they would like to buy our products.
 By creating a trust link with a credit source at the minimum limit that doesn't hinder transactions, we are getting credit for each purchase of our product.
 We get that credit into money at rate \\(R_{ej}\\). By linking to multiple credit sources, we make sure to find enough paths so that all our potential internal purchases are transformed into money.


*comment:* Creating trust links of minimum limit doesn't create any problems at all while at the same time helps to connect with customers that have low value bandwidth toward us.

**Lemma 4** 

* Let \\(R_{tr} < R_{ej}\\) be the rate of transactions that pass through an investor's link to \\(R_j\\) of \\(0_+\\) limit and the link of that investor to his investment \\(R_i\\) in order to be processed.

Then that investor's rate of return due to the above is changed by:
$$R_{ein+1}-R_{ein} + R_{tr}$$

*comment:* This shows that due to the position in the ryaki network, one investment could have a higher external rate of return than another investment because it is used as a path to process transactions.


In **Lemma 3 and 4** we have shown that the rate of return of an investment can be increased by linking to other investment and thus allowing transactions to happen inside the ryaki network. We introduced a very small limit per link so that if credit of the initial investment is exchanged with \\(R_j\\)'s credit, the rate of return of \\(R_j\\) would be great enough to transform it into money immediately. What determines the practical size of that limit?

* Increasing the limit allows more value to pass through this link.
* Increasing the limit too much can leave us with credit in \\(R_j\\) if \\(l > R_j\\).

Thus we need to determine \\(R_j\\) as accurately as possible.

//TODO Add methods to determine \\(R_j\\) more accurately. Specifically the effects of 

* the initial investors \\(m_i\\).
* the internal traversing transactions.
* internal transactions of the product of the investment.

## Determining the profit equation

**lemma 5**

Let \\(i_n\\) the interest rate for the investment of money for one month in exchange for investment credit. (The investment credit has greater risk than a loan because the repayment depends on the sales of the product.)

Then the profit equation for initial investors with invested money \\(M= \\{ m_i|i=1..n \\} \\) in increasing order is computed as below.

Because the algorithm that distributes revenue is the [[fair queue algorithm]], each investor receives the same investor rate of return per month \\(\frac{i_{rri}}{n_i}\\).

We know the amount of the recurring repayment sum and and the present value of the investment. We need to find the number of months it will take to get it back plus the profit. Thus form [Time_value_of_money_formulas](http://en.wikipedia.org/wiki/Time_value_of_money) we have:

$$ m_1 = \frac{i_{rri}}{n_i}\frac{(1+i_n)^n-1}{i_n(1+i_n)^n} $$
$$ m_1i_n(1+i_n)^n = - \frac{i_{rri}}{n_i} + \frac{i_{rri}}{n_i}(1+i_n)^n  $$
$$ (m_1i_n-\frac{i_{rri}}{n_i})(1+i_n)^n = - \frac{i_{rri}}{n_i} $$
$$ (1+i_n)^n = \frac{i_{rri}}{-m_1i_nn_i+i_{rri}}   $$
$$ n = \frac{\ln \frac{i_{rri}}{-m_1i_nn_i+i_{rri}} }{ \ln(1+i_n) } $$

The investor with investment \\(m_1\\) gets this amount of credit:

$$ C_{r1} = \frac{i_{rri}}{n_i} \frac{(1+i_n)^n-1}{i_n}  $$

After \\(n\\) months pass, then all investors have received \\(C_{r1}\\) payments for \\(m_1\\) part of their investment. The rest of their inverstment has increased its value and their current value is:

$$m_i'=(m_i-m_1)(1+i_n)^n$$

Now we have n-1 investors, thus the rate of return per investor increases. We continue recursively to compute the remaining credit amounts that each investor should receive.


*comment:* In this formula we do not take into account the actual number of investors that will have credit in the credit source. Maybe though it is not necessary to do so.


