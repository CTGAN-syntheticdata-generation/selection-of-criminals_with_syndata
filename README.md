# selection-of-criminals_with_syndata
It is a project that virtualizes customs administration data and uses it to study the selection of crime.
관세청에서 제공한 가상데이터를 활용함
Data Schema


<!-- Add a button to toggle between Korean and English versions -->
<button id="toggle-btn">Toggle</button>

<!-- Add elements for the Korean version -->
<div id="korean-version">
  <h1>한글 버전</h1>
  <p>여기에 한글 버전 내용을 입력하세요.</p>
</div>

<!-- Add elements for the English version -->
<div id="english-version" style="display: none;">
  <h1>English Version</h1>
  <p>Enter English version content here.</p>
</div>

<!-- Add JavaScript to handle the toggle button click -->
<script>
  const toggleBtn = document.getElementById("toggle-btn");
  const koreanVersion = document.getElementById("korean-version");
  const englishVersion = document.getElementById("english-version");

  toggleBtn.addEventListener("click", () => {
    if (koreanVersion.style.display === "none") {
      // Switch to Korean version
      koreanVersion.style.display = "block";
      englishVersion.style.display = "none";
    } else {
      // Switch to English version
      koreanVersion.style.display = "none";
      englishVersion.style.display = "block";
    }
  });
</script>
