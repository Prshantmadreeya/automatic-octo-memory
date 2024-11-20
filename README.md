# automatic-octo-memory
<!DOCTYPE html>
<html lang="gu">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>રોજ ની રોજગારી</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      margin: 0;
      padding: 0;
      text-align: center;
    }
    header {
      background-color: #007bff;
      color: white;
      padding: 20px 0;
    }
    header h1 {
      margin: 0;
      font-size: 24px;
    }
    .container {
      margin: 20px auto;
      max-width: 800px;
      padding: 20px;
      background: white;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
    }
    .input-group {
      margin-bottom: 15px;
      text-align: left;
    }
    .input-group label {
      display: block;
      font-size: 16px;
      margin-bottom: 5px;
    }
    .input-group input, .input-group textarea {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .btn {
      background-color: #007bff;
      color: white;
      border: none;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
    }
    .btn:hover {
      background-color: #0056b3;
    }
    .jobs-list {
      text-align: left;
    }
    .job-item {
      border: 1px solid #ccc;
      padding: 10px;
      margin-bottom: 10px;
      border-radius: 5px;
    }
    footer {
      background-color: #f4f4f4;
      padding: 10px 0;
      font-size: 14px;
    }
  </style>
</head>
<body>
  <header>
    <h1>રોજ ની રોજગારી</h1>
  </header>

  <div class="container">
    <h2>નવો નોકરી પોસ્ટ કરો</h2>
    <form id="postJobForm">
      <div class="input-group">
        <label for="jobTitle">નોકરીનું નામ:</label>
        <input type="text" id="jobTitle" placeholder="નોકરીનું નામ લખો" required>
      </div>
      <div class="input-group">
        <label for="jobDescription">વર્ણન:</label>
        <textarea id="jobDescription" placeholder="નોકરીની વિગતો લખો" rows="5" required></textarea>
      </div>
      <div class="input-group">
        <label for="jobLocation">સ્થાન:</label>
        <input type="text" id="jobLocation" placeholder="સ્થાન લખો" required>
      </div>
      <button type="submit" class="btn">પોસ્ટ કરો</button>
    </form>
  </div>

  <div class="container">
    <h2>કારિગર શોધો</h2>
    <div id="jobsList" class="jobs-list">
      <!-- Jobs will be displayed here -->
    </div>
  </div>

  <footer>
    <p>© 2024 રોજ ની રોજગારી. સર્વ હક જણાવેલા.</p>
  </footer>

  <script>
    const jobForm = document.getElementById('postJobForm');
    const jobsList = document.getElementById('jobsList');

    let jobs = []; // Store jobs locally

    jobForm.addEventListener('submit', (e) => {
      e.preventDefault();

      const jobTitle = document.getElementById('jobTitle').value;
      const jobDescription = document.getElementById('jobDescription').value;
      const jobLocation = document.getElementById('jobLocation').value;

      const job = { title: jobTitle, description: jobDescription, location: jobLocation };
      jobs.push(job);

      jobForm.reset();
      displayJobs();
    });

    function displayJobs() {
      jobsList.innerHTML = '';
      jobs.forEach((job) => {
        const jobItem = document.createElement('div');
        jobItem.classList.add('job-item');
        jobItem.innerHTML = `
          <h3>${job.title}</h3>
          <p><strong>વર્ણન:</strong> ${job.description}</p>
          <p><strong>સ્થાન:</strong> ${job.location}</p>
        `;
        jobsList.appendChild(jobItem);
      });
    }
  </script>
</body>
</html>
