<!DOCTYPE html> 
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Requirements Checklist</title>
    <style>
        body {
            font-family: 'Angsana New', serif; /* Set font style */
            margin: 20px;
            padding: 20px;
            border: 1.5px solid #ccc;
            border-radius: 5px;
            max-width: 900px;
            background-image: url('https://cdn.wallpapersafari.com/61/57/BvlxOm.jpg');
            background-size: cover;
            background-position: mid top;
            color: black; /* Change text color to black */
        }
        h1 {
            font-size: 24px;
            text-align: center;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            margin: 10px 0;
            transition: color 0.3s;
        }
        input[type="checkbox"] {
            margin-right: 10px;
            accent-color: white; /* Change checkbox color to white */
        }
        .completed {
            color: green; /* Color for completed items */
        }
        .unchecked {
            color: red; /* Color for unchecked items */
        }
    </style>
</head>
<body>

    <h1>Checklist of Requirements for Call-up Order</h1>

    <ul id="checklist">
        <li><input type="checkbox" onchange="updateStatus(this)"> FORM 212 - PERSONAL DATA SHEET (Revised 2017). PROPERLY ACCOMPLISHED, WITH CSC PRESCRIBED PASSPORT SIZE PICTURE (NOTARIZED) - 3 copies</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> WORK EXPERIENCE SHEET (page 5 of Form 212-PDS) - 3 copies</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> PRC RATING/CSC ELIGIBILITY (AUTHENTICATED) - 1 copy original and 2 photocopies</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> PRC LICENSE (AUTHENTICATED, UNEXPIRED) - 1 original and 2 photocopies</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> TMC1 AND NC II CERTIFICATE (AUTHENTICATED) - for SHS TVL track</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> SWORN STATEMENT WITH DOC STAMP (NOTARIZED) - 2 copies</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> OFFICIAL TRANSCRIPT OF RECORDS (AUTHENTICATED and CAV) - 2 copies</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> APPROVED COPY OF GSIS RETIREMENT OF THE INCUMBENT, APPOINTMENT IF PROMOTED, SEPARATION ORDER IF SEPARATED THROUGH DEATH, TRANSFER OR RESIGNATION - 2 copies</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> CS FORM 211 - MEDICAL CERTIFICATE (Use Revised 2018) - 2 copies - Neuro/Psycho Test</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> CS FORM 211 - MEDICAL CERTIFICATE (Use Revised 2018) - 2 copies - Drug Test</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> CS FORM 211 - MEDICAL CERTIFICATE (Use Revised 2018) - 2 copies - Blood Test</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> CS FORM 211 - MEDICAL CERTIFICATE (Use Revised 2018) - 2 copies - Urinalysis</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> CS FORM 211 - MEDICAL CERTIFICATE (Use Revised 2018) - 2 copies - X-ray Test</li>
                <li><input type="checkbox" onchange="updateStatus(this)"> NBI CLEARANCE (Authenticated) if from other Division/Agency - 1 copy</li>
        <li><input type="checkbox" onchange="updateStatus(this)"> BIRTH CERTIFICATE (PSA AUTHENTICATED) - 1 copy</li>
    </ul>

    <div id="status"></div>

    <script>
        function updateStatus(checkbox) {
            const listItem = checkbox.parentNode;
            if (checkbox.checked) {
                listItem.classList.add('completed'); // Add completed class
                listItem.classList.remove('unchecked'); // Remove unchecked class
                listItem.style.color = 'green'; // Change color to green
            } else {
                listItem.classList.remove('completed'); // Remove completed class
                listItem.classList.add('unchecked'); // Add unchecked class
                listItem.style.color = 'red'; // Change color to red
            }

            const statusDiv = document.getElementById('status');
            const checklistItems = document.querySelectorAll('#checklist input[type="checkbox"]');
            const completedCount = Array.from(checklistItems).filter(item => item.checked).length;
            const uncheckedCount = checklistItems.length - completedCount;

            statusDiv.textContent = `${completedCount} requirements completed, ${uncheckedCount} requirements still pending.`;
        }
    </script>

</body>
</html>
