<html>
    <head>
        <meta name="viewport" content="width=device-width, initiaç-scale=1"/> 
        <meta http-equiv="refresh" content="30"/>
        
        <style>
            body {background-color: black;background-repeat: no-repeat;background-position: top left;} 
            h1, h2 {text-align: center;font-family: arial,sans-serif;color:#ffffff;background-color: #000;} 
            p {color:#ffffff;text-align: center;font-family: Georgia, 'Times New Roman', Times, serif;font-size: 48px;font-style: normal;font-weight: 2;}
        </style>
    </head>
    <body>
        <h1>Get your meme!</h1>
        <h2 id="title"></h2>
        <p>Take that and go away!</p>
        <p><img id="url" src="#"></p> <p id="subreddit">Current Subreddit: </p>
    </body>
    <script> 
        const request = async(link) => { 
            const response = await fetch(link); const json = await response.json(); return json;
        }
        
        const getRandomMeme = async() => {
            return request(`https://meme-api.com/gimme`);
        }

        const main = async() => { 
            let meme = await getRandomMeme(); 
            document.getElementById('title').innerHTML = meme.title; 
            document.getElementById('url').src = meme.url; 
            document.getElementById('subreddit').innerHTML += meme.subreddit;
        } 
            main();
    </script>
</html>
