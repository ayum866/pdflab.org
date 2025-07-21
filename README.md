FREE IMAGE TO PDF MAKER NO SING UP NEEDED.
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Live Image Preview</title>
  <style>
    * {
      box-sizing: border-box;
    }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f8f9fa;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }
    #uploadSection {
      text-align: center;
      padding: 20px;
      background: #fff;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
    }
    h2 {
      color: #343a40;
      margin-bottom: 15px;
    }
    input[type="file"] {
      padding: 10px;
      border: 2px dashed #6c757d;
      background-color: #f1f3f5;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    input[type="file"]:hover {
      background-color: #e9ecef;
    }
    #preview {
      width: 100vw;
      height: 100vh;
      object-fit: contain;
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      z-index: 1;
      background-color: #000;
    }
    #printButton {
      display: none;
      position: fixed;
      top: 20px;
      right: 20px;
      padding: 12px 24px;
      font-size: 16px;
      font-weight: 500;
      background-color: #198754;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      z-index: 2;
      box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
      transition: background-color 0.3s;
    }
    #printButton:hover {
      background-color: #157347;
    }
    @media print {
      #printButton {
        display: none !important;
      }
      body, html {
        margin: 0;
        padding: 0;
        background: white !important;
      }
      #preview {
        position: relative;
        width: 100%;
        height: auto;
        background: none !important;
      }
    }
  </style>
</head>
<body>
  <H1>PDF LAB</H1>

  <div id="uploadSection">
    <h2>Select an image to CONVERT:</h2>
    <input type="file" id="imageInput" accept="image/*">
  </div>

  <img id="preview" alt="Image Preview">
  <button id="printButton" onclick="window.print()">Print Image</button>

  <script>
    const input = document.getElementById('imageInput');
    const preview = document.getElementById('preview');
    const uploadSection = document.getElementById('uploadSection');
    const printButton = document.getElementById('printButton');

    input.addEventListener('change', function () {
      const file = this.files[0];
      if (file) {
        const reader = new FileReader();

        reader.addEventListener('load', function () {
          preview.src = reader.result;
          preview.style.display = 'block';
          uploadSection.style.display = 'none';
          printButton.style.display = 'block';
        });

        reader.readAsDataURL(file);
      } else {
        preview.style.display = 'none';
        preview.src = '';
        uploadSection.style.display = 'block';
        printButton.style.display = 'none';
      }
    });
  </script>

</body>
</html>
