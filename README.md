<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Portfolio</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #121212;
            margin: 0;
            padding: 20px;
        }
        h1 {
            font-size: 2.5em;
            text-align: center;
            background: linear-gradient(to right, #4CAF50, #81C784);
            color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            margin-bottom: 20px;
        }
        .portfolio {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
        }
        .portfolio-item {
            background: white;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            width: 30%;
            padding: 10px;
            position: relative;
        }
        .portfolio-item img {
            width: 100%;
            border-radius: 5px;
        }
        .comments {
            margin-top: 10px;
        }
        .comment {
            margin: 5px 0;
        }
        input[type="text"] {
            width: 80%;
            padding: 5px;
        }
        button {
            padding: 5px 10px;
            cursor: pointer;
        }
        .like-button {
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <h1>Dark_Stin</h1>
    <div class="portfolio">
        <div class="portfolio-item">
            <img src="https://assets.onecompiler.app/428jfxyd6/438as7pep/IMG_4061.jpg" alt="Portfolio Item 1">
            <button class="like-button" onclick="likePost(this)">Like (<span>0</span>)</button>
            <div class="comments">
                <div id="comments1"></div>
                <input type="text" id="commentInput1" placeholder="Add a comment">
                <button onclick="addComment(1)">Submit</button>
            </div>
        </div>
        <div class="portfolio-item">
            <img src="https://assets.onecompiler.app/428jfxyd6/438as7pep/IMG_4063.jpg" alt="Portfolio Item 2">
            <button class="like-button" onclick="likePost(this)">Like (<span>0</span>)</button>
            <div class="comments">
                <div id="comments2"></div>
                <input type="text" id="commentInput2" placeholder="Add a comment">
                <button onclick="addComment(2)">Submit</button>
            </div>
        </div>
        <div class="portfolio-item">
            <img src="https://assets.onecompiler.app/428jfxyd6/438as7pep/IMG-20201002-WA0013%202.jpg" alt="Portfolio Item 3">
            <button class="like-button" onclick="likePost(this)">Like (<span>0</span>)</button>
            <div class="comments">
                <div id="comments3"></div>
                <input type="text" id="commentInput3" placeholder="Add a comment">
                <button onclick="addComment(3)">Submit</button>
            </div>
        </div>
        <div class="portfolio-item">
            <img src="https://assets.onecompiler.app/428jfxyd6/438as7pep/IMG_4058.jpg" alt="Portfolio Item 4">
            <button class="like-button" onclick="likePost(this)">Like (<span>0</span>)</button>
            <div class="comments">
                <div id="comments4"></div>
                <input type="text" id="commentInput4" placeholder="Add a comment">
                <button onclick="addComment(4)">Submit</button>
            </div>
        </div>
        <div class="portfolio-item">
            <img src="https://via.placeholder.com/300" alt="Portfolio Item 5">
            <button class="like-button" onclick="likePost(this)">Like (<span>0</span>)</button>
            <div class="comments">
                <div id="comments5"></div>
                <input type="text" id="commentInput5" placeholder="Add a comment">
                <button onclick="addComment(5)">Submit</button>
            </div>
        </div>
    </div>

    <script>
        function likePost(button) {
            const span = button.getElementsByTagName('span')[0];
            let count = parseInt(span.innerText);
            count++;
            span.innerText = count;
        }

        function addComment(postNumber) {
            const input = document.getElementById(`commentInput${postNumber}`);
            const commentText = input.value;
            if (commentText) {
                const commentDiv = document.createElement('div');
                commentDiv.classList.add('comment');
                commentDiv.innerText = commentText;
                document.getElementById(`comments${postNumber}`).appendChild(commentDiv);
                input.value = '';  // Clear input
            }
        }
    </script>

</body>
</html>
