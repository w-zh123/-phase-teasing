# -phase-teasing
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Phase 1 - Uncharted Theme Teasing Calendar</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #2a1810 0%, #1a0f08 100%);
            color: #fff;
            line-height: 1.6;
            padding: 20px;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            margin-bottom: 40px;
            padding: 30px;
            border: 3px solid #d4a574;
            border-radius: 10px;
            background: linear-gradient(135deg, rgba(212, 165, 116, 0.15) 0%, rgba(184, 134, 11, 0.1) 100%);
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '🗺️';
            position: absolute;
            top: -20px;
            right: -20px;
            font-size: 150px;
            opacity: 0.1;
        }

        h1 {
            color: #d4a574;
            font-size: 2.8em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
            font-weight: bold;
            letter-spacing: 2px;
        }

        .subtitle {
            color: #b8a60b;
            font-size: 1.3em;
            margin-bottom: 10px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.8);
        }

        .theme-badge {
            display: inline-block;
            background: linear-gradient(135deg, #d4a574 0%, #b8a60b 100%);
            color: #1a0f08;
            padding: 10px 25px;
            border-radius: 25px;
            font-weight: bold;
            margin-top: 10px;
            box-shadow: 0 4px 15px rgba(212, 165, 116, 0.3);
        }

        .goal-box {
            background: linear-gradient(135deg, rgba(212, 165, 116, 0.25) 0%, rgba(184, 134, 11, 0.15) 100%);
            padding: 25px;
            border-left: 5px solid #d4a574;
            border-radius: 8px;
            margin-bottom: 35px;
            border: 2px solid #d4a574;
        }

        .goal-title {
            color: #d4a574;
            font-weight: bold;
            margin-bottom: 15px;
            font-size: 1.3em;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
        }

        .goal-content {
            color: #e8d4b8;
        }

        .goal-content ul {
            margin-left: 20px;
            margin-top: 12px;
        }

        .goal-content li {
            margin-bottom: 10px;
        }

        .timeline-container {
            margin-bottom: 40px;
        }

        .timeline-title {
            color: #d4a574;
            font-size: 1.8em;
            margin-bottom: 25px;
            text-align: center;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
            font-weight: bold;
        }

        .day-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .day-card {
            background: linear-gradient(135deg, rgba(212, 165, 116, 0.12) 0%, rgba(184, 134, 11, 0.08) 100%);
            border: 2px solid #d4a574;
            border-radius: 12px;
            padding: 25px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.5);
            transition: 0.3s;
        }

        .day-card:hover {
            border-color: #b8a60b;
            box-shadow: 0 12px 30px rgba(212, 165, 116, 0.2);
            transform: translateY(-5px);
        }

        .day-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent 30%, rgba(212, 165, 116, 0.05) 50%, transparent 70%);
            pointer-events: none;
        }

        .day-number {
            color: #d4a574;
            font-size: 2.2em;
            font-weight: bold;
            margin-bottom: 12px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
        }

        .day-label {
            color: #b8a60b;
            font-size: 1em;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-weight: bold;
        }

        .task-item {
            background: rgba(0, 0, 0, 0.4);
            padding: 15px;
            margin-bottom: 12px;
            border-radius: 6px;
            border-left: 3px solid #d4a574;
            color: #e8d4b8;
            font-size: 0.95em;
            line-height: 1.5;
        }

        .task-item strong {
            color: #d4a574;
        }

        .content-type {
            display: inline-block;
            background: linear-gradient(135deg, #d4a574 0%, #b8a60b 100%);
            color: #1a0f08;
            padding: 6px 14px;
            border-radius: 4px;
            font-size: 0.8em;
            font-weight: bold;
            margin-right: 8px;
            margin-bottom: 12px;
            box-shadow: 0 3px 10px rgba(212, 165, 116, 0.3);
        }

        .icon {
            font-size: 2.5em;
            margin-bottom: 12px;
        }

        .summary-box {
            background: linear-gradient(135deg, rgba(212, 165, 116, 0.18) 0%, rgba(184, 134, 11, 0.12) 100%);
            border: 2px solid #d4a574;
            border-radius: 12px;
            padding: 30px;
            margin-top: 40px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.5);
        }

        .summary-title {
            color: #d4a574;
            font-size: 1.5em;
            margin-bottom: 20px;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
        }

        .summary-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
            color: #e8d4b8;
        }

        .summary-item {
            background: rgba(0, 0, 0, 0.4);
            padding: 18px;
            border-radius: 8px;
            border-left: 3px solid #d4a574;
        }

        .summary-item strong {
            color: #d4a574;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
            gap: 15px;
            margin-top: 25px;
        }

        .stat-box {
            background: rgba(0, 0, 0, 0.4);
            padding: 18px;
            border-radius: 8px;
            text-align: center;
            border: 2px solid #d4a574;
        }

        .stat-number {
            color: #d4a574;
            font-size: 2.2em;
            font-weight: bold;
        }

        .stat-label {
            color: #b8a60b;
            font-size: 0.9em;
            margin-top: 8px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .tips {
            background: rgba(0, 0, 0, 0.4);
            border-left: 4px solid #d4a574;
            padding: 22px;
            border-radius: 8px;
            margin-top: 25px;
            color: #e8d4b8;
            border: 2px solid #d4a574;
        }

        .tips strong {
            color: #d4a574;
        }

        .tips ul {
            margin-left: 20px;
            margin-top: 12px;
        }

        .tips li {
            margin-bottom: 10px;
        }

        .uncharted-theme {
            background: linear-gradient(135deg, rgba(139, 69, 19, 0.2) 0%, rgba(184, 134, 11, 0.15) 100%);
            border: 2px dashed #d4a574;
            padding: 20px;
            border-radius: 8px;
            margin: 20px 0;
            color: #e8d4b8;
        }

        .uncharted-theme strong {
            color: #d4a574;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2em;
            }

            .day-cards {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>🗺️ ESEN Brain Games Expo</h1>
            <p class="subtitle">Uncharted 4: A Thief's End Theme</p>
            <span class="theme-badge">Adventure & Treasure Hunt Vibes</span>
        </header>

        <div class="goal-box">
            <div class="goal-title">🎮 Phase 1 Goal: Build Adventure Curiosity</div>
            <div class="goal-content">
                <p>Use the Uncharted 4 treasure hunt aesthetic to create mystery and excitement. Make it look like an adventure game is coming!</p>
                <ul>
                    <li>🗺️ Treasure map & adventure visuals</li>
                    <li>💰 Gold/bronze colors (matching Uncharted palette)</li>
                    <li>🔍 "Clues" and "puzzle" elements from the game</li>
                    <li>⏱️ Countdown with adventure theme</li>
                    <li>🏴‍☠️ Pirate/explorer vibes</li>
                </ul>
            </div>
        </div>

        <div class="uncharted-theme">
            <strong>🎨 Visual Style Guide:</strong><br>
            Colors: Gold (#d4a574), Brown (#8b4513), Dark Brown (#3e2723), Burnt Orange (#cc5500)<br>
            Fonts: Bold, adventure-style fonts<br>
            Elements: Treasure maps, compasses, old letters, gold coins, adventure weapons
        </div>

        <div class="timeline-container">
            <div class="timeline-title">📅 14-Day Adventure Teasing Timeline</div>

            <div class="day-cards">
                <!-- DAY 1 - LOGO POST -->
                <div class="day-card">
                    <div class="icon">🎬</div>
                    <div class="day-number">Day 1</div>
                    <div class="day-label">Logo Reveal</div>
                    <div class="content-type">POST + STORY</div>
                    
                    <div class="task-item">
                        <strong>Post Caption:</strong><br>
                        "The treasure hunt begins... 🗺️✨ ESEN Brain Games Expo is coming! Like Nathan Drake, you'll need to solve puzzles and navigate challenges. Ready for the adventure? #ESENBrainGamesExpo #UnchartedAdventure"
                    </div>
                    <div class="task-item">
                        <strong>Visual:</strong><br>
                        Official logo on treasure map background. Gold & brown Uncharted colors. Add compass rose, old parchment texture.
                    </div>
                    <div class="task-item">
                        <strong>Stories (3-4):</strong><br>
                        • Logo reveal with dramatic effect<br>
                        • Treasure map showing "unknown destination"<br>
                        • Compass pointing to event<br>
                        • "Adventure starts soon" text
                    </div>
                </div>

                <!-- DAY 2-3 -->
                <div class="day-card">
                    <div class="icon">🔍</div>
                    <div class="day-number">Days 2-3</div>
                    <div class="day-label">Mystery Clues</div>
                    <div class="content-type">STORIES</div>
                    
                    <div class="task-item">
                        <strong>Daily Stories (2-3 per day):</strong><br>
                        • "Clue 1: I involve ancient puzzles..." 🧩<br>
                        • "Clue 2: I need strategy & tactics..." ♟️<br>
                        • "Clue 3: I'm a treasure hunt..." 💎<br>
                        • "Clue 4: 3 explorers join forces..." 🗺️
                    </div>
                    <div class="task-item">
                        <strong>Story Elements:</strong><br>
                        Treasure map textures, old letter designs, gold text overlays, adventure music stickers. Use Uncharted game fonts.
                    </div>
                    <div class="task-item">
                        <strong>Engagement:</strong><br>
                        Poll: "What's your treasure?" Question: "Which explorer are you?"
                    </div>
                </div>

                <!-- DAY 4-5 -->
                <div class="day-card">
                    <div class="icon">🎥</div>
                    <div class="day-number">Days 4-5</div>
                    <div class="day-label">Adventure Reel</div>
                    <div class="content-type">REEL + STORIES</div>
                    
                    <div class="task-item">
                        <strong>Reel (20-30 sec):</strong><br>
                        Quick scenes: Drake climbing → solving puzzle → finding treasure → "Found it!" → Logo appears with "Brain Games Expo — February 8"
                    </div>
                    <div class="task-item">
                        <strong>Reel Audio:</strong><br>
                        Adventure music (intense, exploratory vibes). Use a soundtrack with an Uncharted-style vibe.
                    </div>
                    <div class="task-item">
                        <strong>Caption:</strong><br>
                        "The adventure is real. Brain Games Expo is 5 days away. Do you have what it takes? 🗺️⚡ #UnchartedAdventure"
                    </div>
                    <div class="task-item">
                        <strong>Stories:</strong><br>
                        Behind-the-scenes like "preparing the map", "setting traps", "hiding treasures", "D-5 countdown"
                    </div>
                </div>

                <!-- DAY 6-7 -->
                <div class="day-card">
                    <div class="icon">📜</div>
                    <div class="day-number">Days 6-7</div>
                    <div class="day-label">Treasure Map Carousel</div>
                    <div class="content-type">CAROUSEL + STORIES</div>
                    
                    <div class="task-item">
                        <strong>Carousel Post (8 slides):</strong><br>
                        Slide 1: "The Treasure Map" with logo<br>
                        Slide 2: "Zone 1: Chess Challenges" ♟️<br>
                        Slide 3: "Zone 2: Hive Innovation" 🐝💡<br>
                        Slide 4: "Zone 3: Enactus Puzzles" 🧩<br>
                        Slide 5: "Rewards & Treasures" 💰<br>
                        Slide 6: "Date: February 8"<br>
                        Slide 7: "Location: ESEN Campus"<br>
                        Slide 8: "Tag your adventure partner!" 👇
                    </div>
                    <div class="task-item">
                        <strong>Visual Style:</strong><br>
                        Old parchment texture, gold lettering, compass roses, zone markers on maps
                    </div>
                    <div class="task-item">
                        <strong>Stories:</strong><br>
                        "D-3 The stakes are rising", treasure chest animations, zone previews
                    </div>
                </div>

                <!-- DAY 8-9 -->
                <div class="day-card">
                    <div class="icon">🏴‍☠️</div>
                    <div class="day-number">Days 8-9</div>
                    <div class="day-label">Explorer Reveals</div>
                    <div class="content-type">STORIES + POSTS</div>
                    
                    <div class="task-item">
                        <strong>Story Series:</strong><br>
                        • "Meet Explorer #1: CHESS CLUB" ♟️<br>
                        • "Meet Explorer #2: HIVE" 🐝<br>
                        • "Meet Explorer #3: ENACTUS" 🌍<br>
                        • "Together they form... THE CREW"
                    </div>
                    <div class="task-item">
                        <strong>Caption Post:</strong><br>
                        "3 explorers. 3 zones. 1 epic treasure hunt. ESEN Brain Games Expo - Feb 8 🗺️💎 Are you joining the adventure? #ESENBrainGamesExpo #UnchartedAdventure"
                    </div>
                    <div class="task-item">
                        <strong>Stories:</strong><br>
                        Club intro with "D-1" countdown, explorer weapons/tools, team photos with adventure filters
                    </div>
                </div>

                <!-- DAY 10-14 -->
                <div class="day-card">
                    <div class="icon">⚔️</div>
                    <div class="day-number">Days 10-14</div>
                    <div class="day-label">Final Countdown</div>
                    <div class="content-type">DAILY STORIES</div>
                    
                    <div class="task-item">
                        <strong>Multiple Daily Stories (3-4):</strong><br>
                        • "5 days to treasure!", "4 days!", "3 days!", etc.<br>
                        • Quick game clips with adventure music<br>
                        • Poll: "Which zone will you conquer first?"<br>
                        • "Are you ready for adventure?" countdown<br>
                        • Behind-scenes setup like "setting up puzzles"
                    </div>
                    <div class="task-item">
                        <strong>Story Visual Style:</strong><br>
                        Treasure chest opening animations, map animations, "X marks the spot" reveals, Drake running through obstacles
                    </div>
                    <div class="task-item">
                        <strong>Tone:</strong><br>
                        Adventure, excitement, mystery, treasure vibes, explorer spirit
                    </div>
                </div>
            </div>
        </div>

        <div class="summary-box">
            <div class="summary-title">📊 Phase 1 Summary - Uncharted Theme</div>
            
            <div class="stats">
                <div class="stat-box">
                    <div class="stat-number">14</div>
                    <div class="stat-label">Days of Adventure</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">1</div>
                    <div class="stat-label">Logo Post</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">2</div>
                    <div class="stat-label">Regular Posts</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">1</div>
                    <div class="stat-label">Reel</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">1</div>
                    <div class="stat-label">Carousel</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">25+</div>
                    <div class="stat-label">Stories</div>
                </div>
            </div>

            <div class="summary-content" style="margin-top: 25px;">
                <div class="summary-item">
                    <strong>🗺️ Content Breakdown:</strong><br>
                    • 1 logo post (Dec 30)<br>
                    • 2 main posts<br>
                    • 1 adventure reel<br>
                    • 1 treasure map carousel<br>
                    • 25+ daily stories
                </div>
                <div class="summary-item">
                    <strong>📅 Posting Schedule:</strong><br>
                    • Posts: Every 2-3 days<br>
                    • Stories: 2-4 daily<br>
                    • Reel: Day 4-5<br>
                    • Carousel: Day 6-7
                </div>
                <div class="summary-item">
                    <strong>🎨 Uncharted Elements:</strong><br>
                    • Treasure maps & compass<br>
                    • Gold & brown colors<br>
                    • Adventure game vibes<br>
                    • Puzzle elements<br>
                    • Explorer themes
                </div>
            </div>

            <div class="tips">
                <strong>💡 Uncharted Theme Pro Tips:</strong>
                <ul>
                    <li><strong>Color Palette:</strong> Use gold (#d4a574), bronze (#8b4513), burnt orange (#cc5500), dark brown backgrounds</li>
                    <li><strong>Design Elements:</strong> Treasure maps, compass roses, old letters, gold coins, ancient symbols, Drake silhouettes</li>
                    <li><strong>Typography:</strong> Bold, adventure-style fonts. Make it look like game UI</li>
                    <li><strong>Music/Audio:</strong> Use Uncharted-style adventure music (intense, exploratory vibes)</li>
                    <li><strong>Filters:</strong> Use warm, vintage filters for photos. Make everything look "ancient treasure"</li>
                    <li><strong>Text Overlays:</strong> Use phrases like "The hunt begins", "Find your treasure", "Solve the puzzle", "Adventure awaits"</li>
                    <li><strong>Engagement:</strong> Ask "What treasure are you seeking?", "Which zone first?", "Are you ready for adventure?"</li>
                </ul>
            </div>
        </div>
    </div>
</body>
</html>
