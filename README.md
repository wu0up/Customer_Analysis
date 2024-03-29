<h2>使用串流影音的客戶分析</h2>

<h4>1. 目標</h4>
透過IBM樣本資料-Telco Customer Churn Data Set ，探討客戶資料和串流影音使用行為的關係。

<h4>2. 結論</h4>
	透過資料探勘，針對之後串流影音服務的廣告投放標的，可以集中在以下的客群：高資費、合約期長、使用電子帳單的客戶；未來可以利用分類模型，設計協助廣告投放標的的操作介面。

<h4>3. 資料簡介</h4>
     <ul>
     <li>資料筆數：7,043筆</li>
     <li>特徵：</li>
     </ul>
<table>
  <tr>
    <th>類別</th>
    <th>特徵</th>
    <th>資料型態</th>
  </tr>
  <tr>
    <th>電信服務</th>
    <td>Phone, Multiple lines, Internet, Online security, Online backup, Device protection,</br> 
        Tech support, Streaming TV and movies</td>
    <td>類別型</td>
  <tr>
    <th>客戶帳戶資料</th>
    <td>用戶資歷(Tenure)、每月付款金額(Monthly charges)、總付款金額(Total charges)、</br>
        合約型態(Contract)、付款方式(Payment method)、是否使用電子帳單(Paperless billing)</td>
    <td>數字型</br>
        類別型</td>
  </tr>
  <tr>
    <th>客戶基本資料</th>
    <td>性別(Gender)、是否為年長者(Senior)、配偶(Partners)、
        小孩(Dependents)</td>
    <td>類別型</td>
  </tr>
</table>
Reference: https://www.kaggle.com/jsaguiar/exploratory-analysis-with-seaborn/comments

<h4>4. 資料探勘</h4>
    觀察資料中，串流服務的使用比例相近；結合客戶基本資料進行觀察，在年長者的使用者，使用串流影音服務的比例較多，非年長者的客戶群在使用比例上沒有明顯差異；性別資料跟串流影音的使用較沒關係。	
<img src="https://github.com/wu0up/Customer_Analysis/blob/master/Picture/Senior.png" alt=""> 
<h6>Fig. 1 串流影音服務和使用者年齡的關係；標籤0表示沒有使用服務，標籤1表示有使用服務</h6>
<img src="https://github.com/wu0up/Customer_Analysis/blob/master/Picture/gender.png" alt="">
<h6>Fig. 2 串流影音服務和使用者性別的關係；標籤0表示沒有使用服務，標籤1表示有使用服務</h6>
    將串流資料和客戶帳戶資料一起觀察，隨著用戶資歷(Tenure)增加，使用影音串流比例的客戶也有增加；使用影音串流的客戶，屬於每月付款金額較高的客戶群，總付款金額也比沒有使用的客戶群高。
<img src="https://github.com/wu0up/Customer_Analysis/blob/master/Picture/KDE_tenure.png" alt=""> 
<h6>Fig. 3 串流影音服務和用戶資歷的關係</h6>
<img src="https://github.com/wu0up/Customer_Analysis/blob/master/Picture/KDE_totalcharges.png" alt="">
<h6>Fig. 4 串流影音服務和總付款費用的關係</h6>
<img src="https://github.com/wu0up/Customer_Analysis/blob/master/Picture/KDE_Monthlycharges.png" alt="">
<h6>Fig. 5 串流影音服務和每月付款金額的關係</h6>
  合約(Contract)期間越長，使用串流影音的比例越高，且每月付款金額也高；係就使用電子帳單(Paperless Billing)，使用串流影音的比例也超過50%。
<img src="https://github.com/wu0up/Customer_Analysis/blob/master/Picture/contract.png" alt="">
<h6>Fig. 6 串流影音服務、合約長短及每月付款金額比較</h6>
<img src="https://github.com/wu0up/Customer_Analysis/blob/master/Picture/contract_2.png" alt="">
<h6>Fig. 7 串流影音服務和電子帳單使用的關係</h6>
<img src="https://github.com/wu0up/Customer_Analysis/blob/master/Picture/heatmap_3.png" alt="">
<h6>Fig. 8 熱力圖，每個特徵和串流影音的相關性</h6>
<h4>5. 模型預測</h4>
    本問題屬於二元分類問題，因此使用Logistic Regression, Support Vector Machine(RBF) 和K-nearest neighbor classification進行預測；Logistic Regression和SVM的測試集精確度高達100%，K-nearest neighbor classification測試集的精確度為84%。
