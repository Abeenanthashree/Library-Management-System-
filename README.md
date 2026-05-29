# Library-Management-System-
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Library Management System</title>

<link rel="stylesheet"
href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:Arial;
}

body{
  display:flex;
  background:linear-gradient(135deg,#e0f7ff,#f3e8ff,#fff4d6);
  overflow-x:hidden;
}

/* SIDEBAR */

.sidebar{
  width:250px;
  height:100vh;
  background:linear-gradient(180deg,#001f54,#0b6efd,#6f42c1);
  color:white;
  padding:20px;
  position:fixed;
  box-shadow:4px 0 15px rgba(0,0,0,0.2);
}

.logo{
  text-align:center;
}

.logo img{
  width:100px;
  animation:float 3s infinite ease-in-out;
}

.logo h2{
  margin-top:10px;
  font-size:28px;
}

.logo p{
  color:#ddd;
}

@keyframes float{

  0%{
    transform:translateY(0px);
  }

  50%{
    transform:translateY(-10px);
  }

  100%{
    transform:translateY(0px);
  }

}

.sidebar ul{
  list-style:none;
  margin-top:40px;
}

.sidebar ul li{
  padding:15px;
  margin-bottom:15px;
  border-radius:12px;
  cursor:pointer;
  transition:0.4s;
  background:rgba(255,255,255,0.1);
}

.sidebar ul li:hover{
  background:white;
  color:#0b6efd;
  transform:translateX(10px);
}

.sidebar ul li i{
  margin-right:10px;
}

/* MAIN */

.main{
  margin-left:250px;
  width:100%;
  padding:25px;
}

/* TOPBAR */

.topbar{
  background:white;
  padding:20px;
  border-radius:20px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  box-shadow:0 4px 15px rgba(0,0,0,0.1);
}

.topbar h1{
  font-size:35px;
  background:linear-gradient(90deg,#0b6efd,#6f42c1,#ff0080);
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

.topbar p{
  color:#666;
}

#darkModeBtn{
  background:linear-gradient(90deg,#ff0080,#6f42c1);
  color:white;
  border:none;
  padding:12px 20px;
  border-radius:30px;
  cursor:pointer;
}

/* CARDS */

.cards{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:20px;
  margin-top:30px;
}

.card{
  padding:30px;
  border-radius:20px;
  color:white;
  text-align:center;
  transition:0.4s;
  box-shadow:0 6px 15px rgba(0,0,0,0.15);
}

.card:hover{
  transform:translateY(-10px);
}

.card i{
  font-size:45px;
  margin-bottom:15px;
}

.card h2{
  font-size:35px;
}

.card:nth-child(1){
  background:linear-gradient(135deg,#0d6efd,#00c6ff);
}

.card:nth-child(2){
  background:linear-gradient(135deg,#ff6a00,#ffb347);
}

.card:nth-child(3){
  background:linear-gradient(135deg,#00b09b,#96c93d);
}

.card:nth-child(4){
  background:linear-gradient(135deg,#8e2de2,#ff0080);
}

/* SEARCH */

.search-box{
  margin-top:30px;
}

.search-box input{
  width:100%;
  padding:18px;
  border:none;
  border-radius:15px;
  box-shadow:0 4px 12px rgba(0,0,0,0.1);
}

/* FORM */

.form-section{
  margin-top:30px;
  background:white;
  padding:25px;
  border-radius:20px;
  box-shadow:0 4px 15px rgba(0,0,0,0.1);
}

.form-section h2{
  color:#0b6efd;
}

form{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:15px;
  margin-top:20px;
}

form input,
form select{
  padding:14px;
  border-radius:12px;
  border:1px solid #ccc;
}

form button{
  background:linear-gradient(90deg,#0b6efd,#6f42c1);
  color:white;
  border:none;
  border-radius:12px;
  cursor:pointer;
}

/* TABLE */

.table-section{
  margin-top:30px;
  background:white;
  padding:25px;
  border-radius:20px;
  box-shadow:0 4px 15px rgba(0,0,0,0.1);
}

table{
  width:100%;
  border-collapse:collapse;
  margin-top:20px;
}

table th{
  background:linear-gradient(90deg,#0b6efd,#6f42c1);
  color:white;
  padding:15px;
}

table td{
  padding:15px;
  text-align:center;
  border-bottom:1px solid #eee;
}

table tr:hover{
  background:#f5f7ff;
}

.available{
  color:green;
  font-weight:bold;
}

.issued{
  color:red;
  font-weight:bold;
}

.deleteBtn{
  background:red;
  color:white;
  border:none;
  padding:8px 15px;
  border-radius:10px;
  cursor:pointer;
}

/* DARK MODE */

.dark{
  background:#111827;
  color:white;
}

.dark .topbar,
.dark .form-section,
.dark .table-section{
  background:#1f2937;
  color:white;
}

.dark input,
.dark select{
  background:#111827;
  color:white;
  border:1px solid #555;
}

/* RESPONSIVE */

@media(max-width:1000px){

  .cards{
    grid-template-columns:repeat(2,1fr);
  }

  form{
    grid-template-columns:repeat(2,1fr);
  }

}

@media(max-width:700px){

  .sidebar{
    display:none;
  }

  .main{
    margin-left:0;
  }

  .cards{
    grid-template-columns:1fr;
  }

  form{
    grid-template-columns:1fr;
  }

}

</style>

</head>

<body>

<!-- SIDEBAR -->

<div class="sidebar">

  <div class="logo">
    <img src="https://cdn-icons-png.flaticon.com/512/2232/2232688.png">
    <h2>Smart Library</h2>
    <p>Management Dashboard</p>
  </div>

  <ul>
    <li><i class="fa-solid fa-house"></i> Dashboard</li>
    <li><i class="fa-solid fa-book"></i> Books</li>
    <li><i class="fa-solid fa-user-graduate"></i> Students</li>
    <li><i class="fa-solid fa-book-open-reader"></i> Issued Books</li>
    <li><i class="fa-solid fa-gear"></i> Settings</li>
  </ul>

</div>

<!-- MAIN -->

<div class="main">

  <!-- TOPBAR -->

  <div class="topbar">

    <div>
      <h1>Library Management System</h1>
      <p>Manage Books, Students & Records</p>
    </div>

    <button id="darkModeBtn">
      🌙 Dark Mode
    </button>

  </div>

  <!-- CARDS -->

  <div class="cards">

    <div class="card">
      <i class="fa-solid fa-book"></i>
      <h2 id="totalBooks">0</h2>
      <p>Total Books</p>
    </div>

    <div class="card">
      <i class="fa-solid fa-book-open"></i>
      <h2 id="issuedBooks">0</h2>
      <p>Issued Books</p>
    </div>

    <div class="card">
      <i class="fa-solid fa-check"></i>
      <h2 id="availableBooks">0</h2>
      <p>Available Books</p>
    </div>

    <div class="card">
      <i class="fa-solid fa-user-graduate"></i>
      <h2 id="studentCount">0</h2>
      <p>Students</p>
    </div>

  </div>

  <!-- SEARCH -->

  <div class="search-box">
    <input type="text" id="searchInput"
    placeholder="Search by title, author or category">
  </div>

  <!-- FORM -->

  <div class="form-section">

    <h2>
      <i class="fa-solid fa-book-medical"></i>
      Add New Book
    </h2>

    <form id="bookForm">

      <input type="text" id="bookName"
      placeholder="Book Name" required>

      <input type="text" id="authorName"
      placeholder="Author Name" required>

      <input type="text" id="bookId"
      placeholder="Book ID" required>

      <input type="text" id="category"
      placeholder="Category" required>

      <input type="text" id="studentName"
      placeholder="Student Name">

      <input type="text" id="rollNumber"
      placeholder="Roll Number">

      <input type="date" id="issueDate">

      <select id="status">
        <option>Available</option>
        <option>Issued</option>
      </select>

      <button type="submit">
        Add Book
      </button>

    </form>

  </div>

  <!-- TABLE -->

  <div class="table-section">

    <h2>
      <i class="fa-solid fa-table"></i>
      Library Records
    </h2>

    <table>

      <thead>

        <tr>
          <th>Book</th>
          <th>Author</th>
          <th>ID</th>
          <th>Category</th>
          <th>Student</th>
          <th>Roll No</th>
          <th>Issue Date</th>
          <th>Status</th>
          <th>Action</th>
        </tr>

      </thead>

      <tbody id="bookTable">

      </tbody>

    </table>

  </div>

</div>

<script>

const form = document.getElementById("bookForm");
const table = document.getElementById("bookTable");

const totalBooks = document.getElementById("totalBooks");
const issuedBooks = document.getElementById("issuedBooks");
const availableBooks = document.getElementById("availableBooks");
const studentCount = document.getElementById("studentCount");

const searchInput = document.getElementById("searchInput");

let total = 0;
let issued = 0;
let available = 0;
let students = 0;

/* ADD BOOK */

form.addEventListener("submit", function(e){

  e.preventDefault();

  const bookName =
  document.getElementById("bookName").value;

  const authorName =
  document.getElementById("authorName").value;

  const bookId =
  document.getElementById("bookId").value;

  const category =
  document.getElementById("category").value;

  const studentName =
  document.getElementById("studentName").value;

  const rollNumber =
  document.getElementById("rollNumber").value;

  const issueDate =
  document.getElementById("issueDate").value;

  const status =
  document.getElementById("status").value;

  let statusClass = "available";

  if(status === "Issued"){
    statusClass = "issued";
    issued++;
  }
  else{
    available++;
  }

  total++;

  if(studentName !== ""){
    students++;
  }

  updateCards();

  const row = document.createElement("tr");

  row.innerHTML = `

    <td>${bookName}</td>
    <td>${authorName}</td>
    <td>${bookId}</td>
    <td>${category}</td>
    <td>${studentName}</td>
    <td>${rollNumber}</td>
    <td>${issueDate}</td>

    <td class="${statusClass}">
      ${status}
    </td>

    <td>
      <button class="deleteBtn">
        Delete
      </button>
    </td>

  `;

  table.appendChild(row);

  row.querySelector(".deleteBtn")
  .addEventListener("click", function(){

    row.remove();

    total--;

    if(status === "Issued"){
      issued--;
    }
    else{
      available--;
    }

    if(studentName !== ""){
      students--;
    }

    updateCards();

  });

  form.reset();

});

/* UPDATE CARDS */

function updateCards(){

  totalBooks.innerText = total;
  issuedBooks.innerText = issued;
  availableBooks.innerText = available;
  studentCount.innerText = students;

}

/* SEARCH */

searchInput.addEventListener("keyup", function(){

  const value =
  searchInput.value.toLowerCase();

  const rows =
  document.querySelectorAll("#bookTable tr");

  rows.forEach(function(row){

    row.style.display =
    row.innerText.toLowerCase().includes(value)
    ? ""
    : "none";

  });

});

/* DARK MODE */

const darkModeBtn =
document.getElementById("darkModeBtn");

darkModeBtn.addEventListener("click", function(){

  document.body.classList.toggle("dark");

});

</script>

</body>
</html>
