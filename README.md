<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>

<h1>Classification of Football Teams on Relegation Battle</h1>

<p>Led a backend project using Machine Learning in a Distributed Database System to classify end-of-season extreme standings of football clubs.</p>

<p><strong>Requirements:</strong> PL/SQL, Oracle</p>
<div class="highlight">
  <h3>Task Approach:</h3>
  <p>Different football leagues feature teams each season, and poorly performing teams face relegation battles. In some leagues, the three teams with the fewest points are relegated, while others survive. This project uses the K Nearest Neighbor (KNN) classification approach to categorize teams as either Relegation Survivors or Relegated, based on criteria derived from data from previous seasons.</p>
</div>

<hr />

<div class="highlight">
  <h3>Database Schema:</h3>
  <h4>Global Schema:</h4>
  <ul>
    <li><strong>Teamlist:</strong> (teamID, teamName, country, seasonId)</li>
    <li><strong>PerformanceList:</strong> (perID, teamID, win, lost, draw, gf, ga, points)</li>
    <li><strong>RelegationBattle:</strong> (relID, perID, rbStatus)</li>
    <li><strong>RecordList:</strong> (recID, win, lost, draw, gf, ga, points, predictedStatus)</li>
  </ul>

  <h4>Fragmentation Schema:</h4>
  <ul>
    <li><strong>Teamlist1:</strong> SLSeasonID=1 Teamlist</li>
    <li><strong>Teamlist2:</strong> SLSeasonID=2 Teamlist</li>
    <li><strong>Teamlist3:</strong> SLSeasonID=3 Teamlist</li>
    <li><strong>PerformanceList1:</strong> SLpoints<35 PerformanceList</li>
    <li><strong>PerformanceList2:</strong> SLpoints>=35 PerformanceList</li>
  </ul>

  <h4>Allocation Schema:</h4>
  <ul>
    <li><strong>Teamlist1, Teamlist2, PerformanceList1, PerformanceList2:</strong> Stored at sites 1 and 2</li>
    <li><strong>RelegationBattle, Record:</strong> Stored at sites 1 and 2</li>
  </ul>
</div>

<hr />

<div class="highlight">
  <h3>Significance of Distributed Database System:</h3>
  <p>Effective classification relies on maintaining accurate data. Distributed database systems facilitate data decentralization, which aids in classification tasks. They offer scalable data management, allowing for efficient data maintenance, expansion, and reliability, which are crucial for accurate predictions compared to centralized systems.</p>
</div>


</body>
</html>
