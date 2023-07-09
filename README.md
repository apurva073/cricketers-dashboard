# cricketers-dashboard
<!DOCTYPE html>
<html>
<head>
    <title>Indian Cricketers Dashboard</title>
    <style>
        body {
            background-color: #f5f5f5;
            text-align: center;
        }

        #dashboard {
            background-color: #fff;
            padding: 20px;
            width: 400px;
            margin: 0 auto;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            border-radius: 5px;
        }

        #search {
            margin-bottom: 20px;
            padding: 5px;
            width: 100%;
        }

        #search-button {
            padding: 5px 10px;
            background-color: #4CAF50;
            color: #fff;
            border: none;
            cursor: pointer;
        }

        #result {
            font-family: Arial, sans-serif;
            text-align: left;
        }

        #result div {
            margin-bottom: 10px;
        }

        h1 {
            color: #4CAF50;
        }
    </style>
</head>
<body>
    <div id="dashboard">
        <h1>Indian Cricketers Dashboard</h1>

        <input type="text" id="search" placeholder="Search cricketer...">
        <button id="search-button">Search</button>
        
        <div id="result"></div>
    </div>

    <script>
        
        var cricketers = [
            { 
                name: "Virat Kohli", 
                instagram: "https://www.instagram.com/virat.kohli/", 
                twitter: "https://twitter.com/imVkohli", 
                birth: "5 November 1988", 
                career: "2008 - Present",
                matches: 254,
                awards: ["Sir Garfield Sobers Trophy (ICC Cricketer of the Year)", "Rajiv Gandhi Khel Ratna Award"]
            },
            { 
                name: "Rohit Sharma", 
                instagram: "https://www.instagram.com/rohitsharma45/", 
                twitter: "https://twitter.com/imRo45", 
                birth: "30 April 1987", 
                career: "2007 - Present",
                matches: 227,
                awards: ["Rajiv Gandhi Khel Ratna Award", "ICC ODI Cricketer of the Year"]
            },
            { 
                name: "Jasprit Bumrah", 
                instagram: "https://www.instagram.com/jaspritb1/", 
                twitter: "https://twitter.com/Jaspritbumrah93", 
                birth: "6 December 1993", 
                career: "2016 - Present",
                matches: 67,
                awards: ["Wisden Leading Cricketer in the World"]
            },
           
            { 
                name: "Shikhar Dhawan", 
                instagram: "https://www.instagram.com/shikhardofficial/", 
                twitter: "https://twitter.com/SDhawan25", 
                birth: "5 December 1985", 
                career: "2010 - Present",
                matches: 145,
                awards: ["Golden Bat (ICC Champions Trophy 2013)"]
            },
            { 
                name: "Hardik Pandya", 
                instagram: "https://www.instagram.com/hardikpandya93/", 
                twitter: "https://twitter.com/hardikpandya7", 
                birth: "11 October 1993", 
                career: "2016 - Present",
                matches: 60,
                awards: ["Arjuna Award"]
            },
            { 
                name: "Ravindra Jadeja", 
                instagram: "https://www.instagram.com/ravindra.jadeja/", 
                twitter: "https://twitter.com/imjadeja", 
                birth: "6 December 1988", 
                career: "2009 - Present",
                matches: 167,
                awards: ["Arjuna Award"]
            },
            { 
                name: "Ajinkya Rahane", 
                instagram: "https://www.instagram.com/ajinkyarahane/", 
                twitter: "https://twitter.com/ajinkyarahane88", 
                birth: "6 June 1988", 
                career: "2011 - Present",
                matches: 73,
                awards: []
            },
            
            { 
                name: "Ravichandran Ashwin", 
                instagram: "https://www.instagram.com/rashwin99/", 
                twitter: "https://twitter.com/ashwinravi99", 
                birth: "17 September 1986", 
                career: "2010 - Present",
                matches: 111,
                awards: ["Sir Garfield Sobers Trophy (ICC Cricketer of the Year)", "ICC Test Cricketer of the Year"]
            },
            { 
                name: "Ishant Sharma", 
                instagram: "https://www.instagram.com/ishant.sharma29/", 
                twitter: "https://twitter.com/imIshant", 
                birth: "2 September 1988", 
                career: "2007 - Present",
                matches: 101,
                awards: []
            },
           
            { 
                name: "Yuzvendra Chahal", 
                instagram: "https://www.instagram.com/yuzi_chahal23/", 
                twitter: "https://twitter.com/yuzi_chahal", 
                birth: "23 July 1990", 
                career: "2016 - Present",
                matches: 54,
                awards: []
            },
           
            { 
                name: "Kuldeep Yadav", 
                instagram: "https://www.instagram.com/kuldeep_18/", 
                twitter: "https://twitter.com/imkuldeep18", 
                birth: "14 December 1994", 
                career: "2017 - Present",
                matches: 61,
                awards: []
            },
            { 
                name: "Mayank Agarwal", 
                instagram: "https://www.instagram.com/mayankagarawal/", 
                twitter: "https://twitter.com/mayankcricket", 
                birth: "16 February 1991", 
                career: "2018 - Present",
                matches: 14,
                awards: []
            },
            { 
                name: "Shubman Gill", 
                instagram: "https://www.instagram.com/shubmangill/", 
                twitter: "https://twitter.com/shubmangill", 
                birth: "8 September 1999", 
                career: "2019 - Present",
                matches: 10,
                awards: []
            },
            { 
                name: "Washington Sundar", 
                instagram: "https://www.instagram.com/washisundar555/", 
                twitter: "https://twitter.com/Sundarwashi5", 
                birth: "5 October 1999", 
                career: "2017 - Present",
                matches: 12,
                awards: []
            },
            { 
                name: "Shardul Thakur", 
                instagram: "https://www.instagram.com/shardul_thakur/", 
                twitter: "https://twitter.com/imShard", 
                birth: "16 October 1991", 
                career: "2018 - Present",
                matches: 22,
                awards: []
            },
            { 
                name: "Prithvi Shaw", 
                instagram: "https://www.instagram.com/prithvishaw/", 
                twitter: "https://twitter.com/PrithviShaw", 
                birth: "9 November 1999", 
                career: "2018 - Present",
                matches: 5,
                awards: []
            },
            { 
                name: "MS Dhoni", 
                instagram: "https://www.instagram.com/mahi7781/", 
                twitter: "https://twitter.com/msdhoni", 
                birth: "7 July 1981", 
                career: "2004 - 2019",
                matches: 350,
                awards: ["Rajiv Gandhi Khel Ratna Award", "Padma Shri", "Padma Bhushan"]
            },
            { 
                name: "Sachin Tendulkar", 
                instagram: "https://www.instagram.com/sachintendulkar/", 
                twitter: "https://twitter.com/sachin_rt", 
                birth: "24 April 1973", 
                career: "1989 - 2013",
                matches: 463,
                awards: ["Bharat Ratna", "Rajiv Gandhi Khel Ratna Award", "Padma Vibhushan"]
            },
            { 
                name: "Ravi Shastri", 
                instagram: "https://www.instagram.com/ravishastriofficial/", 
                twitter: "https://twitter.com/ravishastriofc", 
                birth: "27 May 1962", 
                career: "1981 - 1992",
                matches: 80,
                awards: []
            }
            
        ];

       
        function searchCricketer() {
            var searchQuery = document.getElementById("search").value.toLowerCase();
            var resultDiv = document.getElementById("result");
            resultDiv.innerHTML = "";

            for (var i = 0; i < cricketers.length; i++) {
                var cricketer = cricketers[i];
                var cricketerName = cricketer.name.toLowerCase();

                if (cricketerName.includes(searchQuery)) {
                    var cricketerDiv = document.createElement("div");
                    cricketerDiv.innerHTML = "<h3>" + cricketer.name + "</h3>" +
                        "<p>Birth: " + cricketer.birth + "</p>" +
                        "<p>Career: " + cricketer.career + "</p>" +
                        "<p>Matches: " + cricketer.matches + "</p>" +
                        "<p>Awards: " + (cricketer.awards.length > 0 ? cricketer.awards.join(", ") : "None") + "</p>" +
                        "<p>Instagram: <a href='" + cricketer.instagram + "' target='_blank'>" + cricketer.instagram + "</a></p>" +
                        "<p>Twitter: <a href='" + cricketer.twitter + "' target='_blank'>" + cricketer.twitter + "</a></p>";
                    resultDiv.appendChild(cricketerDiv);
                }
            }
        }

        // Event listener for search button
        document.getElementById("search-button").addEventListener("click", searchCricketer);

        // Event listener for search input
        document.getElementById("search").addEventListener("keyup", function(event) {
            if (event.keyCode === 13) {
                event.preventDefault();
                document.getElementById("search-button").click();
            }
        });
    </script>
</body>
</html>
