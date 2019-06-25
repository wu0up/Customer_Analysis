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
![Alt text](https://github.com/wu0up/Customer_Analysis/blob/master/Picture/Senior.png)
  將串流資料和客戶帳戶資料一起觀察，隨著用戶資歷(Tenure)增加，使用影音串流比例的客戶也有增加；使用影音串流的客戶，屬於每月付款金額較高的客戶群，總付款金額也比沒有使用的客戶群高。
  合約(Contract)期間越長，使用串流影音的比例越高，且每月付款金額也高；係就使用電子帳單(Paperless Billing)，使用串流影音的比例也超過50%。

<h4>5. 模型預測</h4>
	本問題屬於二元分類問題，因此使用Logistic Regression, Support Vector Machine(RBF) 和K-nearest neighbor classification進行預測；Logistic Regression和SVM的測試集精確度高達100%，K-nearest neighbor classification測試集的精確度為84%。
