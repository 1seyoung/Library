
<%*
// Dataview API 참조
const dv = app.plugins.plugins["dataview"].api;

// 첫 번째 쿼리 설정
const filename1 = "중요한 글";
const query1 = `TABLE WITHOUT ID
  file.link AS "제목",
  choice(
    별점,
    "⭐" + 
    choice(별점 >= 2, "⭐", "") + 
    choice(별점 >= 3, "⭐", "") + 
    choice(별점 >= 4, "⭐", "") + 
    choice(별점 = 5, "⭐", ""),
    "-"

  ) AS "중요도"
FROM ""
WHERE 
  별점 >= 3 AND 별점 <= 5 AND
  !startswith(file.folder, "🧣 일상") AND
  !startswith(file.folder, "Obsidian") AND
  !contains(file.name, "🧣 일상") AND
  !contains(file.name, "🪼 project") AND
  !contains(file.name, "🛶 developer") AND
  !contains(file.name, "🌳 coding test") AND
  !contains(file.name, "💾 textbook") AND
  !contains(file.name, "👓 research")
SORT file.mtime DESC
LIMIT 15`;

// 두 번째 쿼리 설정
const filename2 = "최근 작성한 글";
const query2 = `TABLE WITHOUT ID
file.link AS "제목"
FROM ""
WHERE 
!startswith(file.folder, "🧣 일상") AND
!startswith(file.folder, "Obsidian") AND
!contains(file.name, "🧣 일상") AND
!contains(file.name, "🪼 project") AND
!contains(file.name, "🛶 developer") AND
!contains(file.name, "🌳 coding test") AND
!contains(file.name, "💾 textbook") AND
!contains(file.name, "👓 research")
SORT file.mtime DESC
LIMIT 10`;

// 쿼리 실행 및 파일 수정
const tFile1 = tp.file.find_tfile(filename1);
const queryOutput1 = await dv.queryMarkdown(query1);
await app.vault.modify(tFile1, queryOutput1.value);

const tFile2 = tp.file.find_tfile(filename2);
const queryOutput2 = await dv.queryMarkdown(query2);
await app.vault.modify(tFile2, queryOutput2.value);
%>




