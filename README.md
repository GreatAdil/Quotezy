<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>Quotezy App Mockup</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    <style>
        /* --- CSS (Identical to the previous version) --- */
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');

        :root {
            --primary-purple: #A076F9; /* Main purple */
            --light-purple: #E5D4FF; /* Lighter shade for backgrounds/cards */
            --dark-purple: #663399;  /* Deeper purple for accents/text */
            --pastel-pink: #FBC7F7;
            --accent-color: #7F00FF; /* Violet for Create button, etc. */
            --text-color: #333;
            --text-light: #555;
            --text-on-purple: #FFFFFF;
            --white: #FFFFFF;
            --light-gray: #f4f4f8; /* Softer light gray */
            --medium-gray: #e0e0e0;
            --border-radius: 15px;
            --box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
            --font-family: 'Poppins', sans-serif;

            /* Dark Theme Variables */
            --dark-bg: #1f1f2e;
            --dark-card-bg: #2a2a3a;
            --dark-text-color: #e0e0e0;
            --dark-text-light: #b0b0b0;
            --dark-primary-purple: #B39DDB; /* Lighter purple for dark theme */
            --dark-light-purple: #3e3e52;
        }

        body {
            font-family: var(--font-family);
            margin: 0;
            background-color: var(--light-gray);
            color: var(--text-color);
            overflow-x: hidden;
            line-height: 1.6;
            transition: background-color 0.3s, color 0.3s;
        }

        body.dark-theme {
            background-color: var(--dark-bg);
            color: var(--dark-text-color);
        }
        body.dark-theme .card,
        body.dark-theme #create-status-screen .editor-toolbar,
        body.dark-theme #create-status-screen .create-header,
        body.dark-theme #explore-screen .explore-header,
        body.dark-theme #explore-screen .filters,
        body.dark-theme #quote-detail-bottom-sheet,
        body.dark-theme #language-selection-screen,
        body.dark-theme #language-selection-screen .screen-header,
        body.dark-theme #language-selection-screen .continue-button-container,
        body.dark-theme #remove-ads-screen .purchase-card {
            background-color: var(--dark-card-bg);
            color: var(--dark-text-color);
        }
        body.dark-theme h1, body.dark-theme h2, body.dark-theme h3 {
             color: var(--dark-primary-purple);
        }
        body.dark-theme .app-main-header {
             background-color: var(--dark-primary-purple);
             color: var(--dark-bg); /* Ensure contrast */
        }
        body.dark-theme .app-main-header h1 { color: var(--dark-bg); }

        body.dark-theme .text-light { color: var(--dark-text-light); }
        body.dark-theme .bottom-nav { background-color: var(--dark-card-bg); border-top-color: #444;}
        body.dark-theme .nav-item { color: var(--dark-text-light); }
        body.dark-theme .nav-item.active { color: var(--dark-primary-purple); }
        body.dark-theme button, body.dark-theme .button {
            background-color: var(--dark-primary-purple);
            color: var(--dark-bg);
        }
        body.dark-theme button:hover, body.dark-theme .button:hover {
            background-color: #9575CD; /* Slightly darker shade of dark-primary-purple */
        }
        body.dark-theme .home-screen-gradient-bg {
             background: linear-gradient(to bottom, var(--dark-primary-purple) 0%, var(--dark-primary-purple) 150px, var(--dark-bg) 150px, var(--dark-bg) 100%);
        }
        body.dark-theme #home-screen .home-header-greeting h1,
        body.dark-theme #home-screen .home-header-greeting {
            color: var(--dark-bg);
        }
         body.dark-theme #home-screen .quote-card .quote-text { color: var(--dark-text-color); }
         body.dark-theme #home-screen .quote-card .quote-author { color: var(--dark-text-light); }
         body.dark-theme #home-screen .quote-card .quote-meta .category {
            background-color: var(--dark-light-purple);
            color: var(--dark-text-color);
         }
        body.dark-theme #home-screen .explore-preview-item {
            background-color: var(--dark-light-purple);
            color: var(--dark-text-color);
        }
        body.dark-theme #explore-screen .filter-btn {
            background-color: var(--dark-light-purple);
            color: var(--dark-text-color);
        }
        body.dark-theme #explore-screen .filter-btn.active {
            background-color: var(--dark-primary-purple);
            color: var(--dark-bg);
        }
        body.dark-theme #explore-screen .quote-grid-item .author { color: var(--dark-text-light); }

        body.dark-theme #create-status-screen .preview-canvas {
            background: linear-gradient(135deg, #3a506b 0%, #5c9ead 100%); /* Darker gradient */
        }
        body.dark-theme #create-status-screen .tool-item { color: var(--dark-text-light); }
        body.dark-theme #create-status-screen .tool-item.active {
            color: var(--dark-primary-purple);
            background: linear-gradient(to top, var(--dark-light-purple) 0%, transparent 70%);
        }
        body.dark-theme #settings-screen .settings-item i.leading-icon { color: var(--dark-primary-purple); }
        body.dark-theme #settings-screen .settings-item .action-element input:checked + .slider {
            background-color: var(--dark-primary-purple);
        }
         body.dark-theme #language-selection-screen .language-item:hover {
            background-color: var(--dark-light-purple);
        }
        body.dark-theme #language-selection-screen .language-item.selected .checkmark {
            color: var(--dark-primary-purple);
        }
        body.dark-theme #favorites-screen { background-color: var(--dark-light-purple); } /* Darker for contrast */
        body.dark-theme #favorites-screen .favorite-item .quote-text { color: var(--dark-text-color); }
        body.dark-theme #favorites-screen .favorite-item .quote-author { color: var(--dark-text-light); }
        body.dark-theme #favorites-screen .favorite-item .actions i:hover { color: var(--dark-primary-purple); }
        body.dark-theme #favorites-screen .favorite-item .category-tag {
            background-color: var(--dark-card-bg); /* Match card bg */
            color: var(--dark-text-color);
            border: 1px solid var(--dark-light-purple); /* Subtle border */
        }
        body.dark-theme #splash-screen {
            background: linear-gradient(135deg, var(--dark-primary-purple), var(--dark-light-purple));
        }
        body.dark-theme #onboarding-screen-1 {
            background-color: var(--dark-light-purple);
        }
         body.dark-theme #onboarding-screen-1 .illustration {
             background-color: var(--dark-card-bg);
             color: var(--dark-primary-purple);
         }
        body.dark-theme #onboarding-screen-1 h2 { color: var(--dark-primary-purple); }
        body.dark-theme #onboarding-screen-1 p { color: var(--dark-text-light); }
        body.dark-theme #onboarding-screen-1 .dot { background-color: var(--dark-primary-purple); }

        body.dark-theme #quote-detail-bottom-sheet .action-button {
            background-color: var(--dark-light-purple);
            color: var(--dark-text-color);
        }
        body.dark-theme #quote-detail-bottom-sheet .action-button:hover {
            background-color: var(--dark-primary-purple);
            color: var(--dark-bg);
        }

        .app-screen { display: none; min-height: 100vh; width: 100%; box-sizing: border-box; overflow-y: auto; padding-bottom: 70px; }
        .app-screen.active { display: flex; flex-direction: column; }
        .app-screen.no-bottom-padding { padding-bottom: 0; }
        .screen-content { padding: 20px; flex-grow: 1; }
        h1, h2, h3 { color: var(--dark-purple); margin-top: 0; }
        h1 { font-size: 24px; font-weight: 600; }
        h2 { font-size: 20px; font-weight: 500; }
        h3 { font-size: 18px; font-weight: 500; }
        button, .button { background-color: var(--primary-purple); color: var(--text-on-purple); border: none; padding: 12px 20px; border-radius: var(--border-radius); font-size: 16px; cursor: pointer; transition: background-color 0.3s ease, transform 0.1s ease; font-family: var(--font-family); font-weight: 500; text-align: center; text-decoration: none; display: inline-block; }
        button:hover, .button:hover { background-color: var(--dark-purple); }
        button:active, .button:active { transform: scale(0.98); }
        .card { background-color: var(--white); border-radius: var(--border-radius); padding: 15px; margin-bottom: 15px; box-shadow: var(--box-shadow); transition: background-color 0.3s; }
        .bottom-nav { position: fixed; bottom: 0; left: 0; right: 0; background-color: var(--white); display: flex; justify-content: space-around; align-items: center; height: 60px; box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.1); border-top: 1px solid var(--medium-gray); z-index: 1000; transition: background-color 0.3s, border-top-color 0.3s; }
        .nav-item { display: flex; flex-direction: column; align-items: center; justify-content: center; color: var(--text-light); cursor: pointer; flex: 1; padding: 5px 0; font-size: 12px; transition: color 0.3s; }
        .nav-item i { font-size: 20px; margin-bottom: 3px; }
        .nav-item.active { color: var(--primary-purple); }
        .app-main-header { padding: 15px 20px; background-color: var(--primary-purple); color: var(--text-on-purple); transition: background-color 0.3s, color 0.3s; }
        .app-main-header h1 { font-size: 22px; margin: 0; color: var(--text-on-purple); font-weight: 600; transition: color 0.3s; }

        #splash-screen { background: linear-gradient(135deg, var(--primary-purple), var(--pastel-pink)); justify-content: center; align-items: center; text-align: center; color: var(--text-on-purple); padding-bottom: 0; transition: background 0.3s; }
        #splash-screen .logo { font-size: 48px; font-weight: 700; margin-bottom: 10px; background: linear-gradient(90deg, #fff, #eee, #fff); background-size: 200% 100%; -webkit-background-clip: text; background-clip: text; color: transparent; animation: shimmer 3s infinite linear; }
        #splash-screen .tagline { font-size: 18px; font-weight: 300; }
        @keyframes shimmer { 0% { background-position: 200% 0; } 100% { background-position: -200% 0; } }

        #onboarding-screen-1 { background-color: var(--light-purple); justify-content: center; align-items: center; text-align: center; padding: 30px 20px; transition: background-color 0.3s; }
        #onboarding-screen-1 .onboarding-content { max-width: 320px; }
        #onboarding-screen-1 .illustration { width: 180px; height: 180px; background-color: var(--white); border-radius: 50%; display: flex; justify-content: center; align-items: center; font-size: 50px; color: var(--primary-purple); margin: 0 auto 30px auto; box-shadow: var(--box-shadow); transition: background-color 0.3s, color 0.3s; }
        #onboarding-screen-1 h2 { font-size: 24px; color: var(--dark-purple); margin-bottom: 15px; }
        #onboarding-screen-1 p { font-size: 16px; color: var(--text-light); margin-bottom: 30px; }
        #onboarding-screen-1 .nav-dots { margin-bottom: 30px; }
        #onboarding-screen-1 .dot { display: inline-block; width: 10px; height: 10px; background-color: var(--primary-purple); border-radius: 50%; margin: 0 5px; opacity: 0.5; }
        #onboarding-screen-1 .dot.active { opacity: 1; }
        #onboarding-screen-1 .next-button { width: 100%; }

        #language-selection-screen { background-color: var(--white); flex-direction: column; }
        #language-selection-screen .screen-header { text-align: center; padding: 20px; font-size: 22px; font-weight: 600; color: var(--dark-purple); border-bottom: 1px solid var(--medium-gray); }
        #language-selection-screen .screen-content { flex-grow: 1; overflow-y: auto; padding: 0; }
        #language-selection-screen .language-list { list-style: none; padding: 0; margin: 0; }
        #language-selection-screen .language-item { display: flex; justify-content: space-between; align-items: center; padding: 15px 20px; border-bottom: 1px solid var(--light-gray); cursor: pointer; }
        #language-selection-screen .language-item:hover { background-color: var(--light-purple); }
        #language-selection-screen .language-item span { font-size: 16px; }
        #language-selection-screen .language-item .flag { margin-right: 10px; }
        #language-selection-screen .language-item .checkmark { color: var(--primary-purple); font-size: 20px; visibility: hidden; }
        #language-selection-screen .language-item.selected .checkmark { visibility: visible; }
        #language-selection-screen .continue-button-container { padding: 20px; background-color: var(--white); border-top: 1px solid var(--medium-gray); }
        #language-selection-screen .continue-button { width: 100%; }

        .home-screen-gradient-bg { background: linear-gradient(to bottom, var(--primary-purple) 0%, var(--primary-purple) 150px, var(--light-gray) 150px, var(--light-gray) 100%); min-height: 100vh; display: flex; flex-direction: column; }
        #home-screen .home-header-greeting { padding: 25px 20px 15px 20px; color: var(--text-on-purple); }
        #home-screen .home-header-greeting h1 { font-size: 28px; font-weight: 600; margin: 0; color: var(--text-on-purple); }
        #home-screen .create-status-button { display: block; width: calc(100% - 40px); margin: 0px auto 20px auto; padding: 15px; font-size: 18px; background-color: var(--accent-color); box-shadow: 0 4px 10px rgba(127,0,255,0.4); }
        #home-screen .quote-card { margin: 0 20px 15px 20px; }
        #home-screen .quote-card h3 { font-size: 16px; margin-bottom: 5px; }
        #home-screen .quote-card .quote-text { font-size: 15px; margin-bottom: 10px; line-height: 1.4; }
        #home-screen .quote-card .quote-author { font-size: 13px; color: var(--text-light); font-style: italic; margin-bottom: 10px; text-align: right; }
        #home-screen .quote-card .quote-actions { display: flex; justify-content: flex-end; gap: 15px; margin-top: 8px; }
        #home-screen .quote-card .quote-actions i { font-size: 18px; color: var(--text-light); cursor: pointer; }
        #home-screen .quote-card .quote-actions i:hover { color: var(--primary-purple); }
        #home-screen .quote-card .quote-actions .fa-heart.favorited { color: var(--pastel-pink); }
        #home-screen .quote-card .quote-meta { display: flex; justify-content: space-between; align-items: center; font-size: 12px; color: var(--text-light); }
        #home-screen .quote-card .quote-meta .category { background-color: var(--light-purple); color: var(--dark-purple); padding: 3px 8px; border-radius: 5px; }
        #home-screen .quote-card .quote-meta .likes i { color: var(--pastel-pink); margin-right: 3px; }
        #home-screen .section-title { font-size: 20px; font-weight: 600; color: var(--dark-purple); margin: 25px 20px 10px 20px; }
        #home-screen .explore-preview { padding: 0 20px; display: flex; gap: 10px; overflow-x: auto; padding-bottom: 10px; }
        #home-screen .explore-preview-item { min-width: 120px; height: 80px; background-color: var(--light-purple); border-radius: 10px; display: flex; justify-content: center; align-items: center; color: var(--dark-purple); font-weight: 500; box-shadow: var(--box-shadow); cursor: pointer; transition: background-color 0.3s, color 0.3s; }

        #explore-screen .explore-header { padding: 15px 20px; background-color: var(--white); box-shadow: 0 2px 4px rgba(0,0,0,0.05); }
        #explore-screen .explore-header h1 { margin: 0; }
        #explore-screen .filters { display: flex; gap: 10px; padding: 15px 20px; background-color: var(--white); overflow-x: auto; border-bottom: 1px solid var(--medium-gray); white-space: nowrap; }
        #explore-screen .filter-btn { padding: 8px 15px; background-color: var(--light-purple); color: var(--dark-purple); border-radius: 20px; font-size: 14px; }
        #explore-screen .filter-btn.active { background-color: var(--primary-purple); color: var(--text-on-purple); }
        #explore-screen .quote-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); gap: 15px; padding: 20px; }
        #explore-screen .screen-content { padding: 0; }
        #explore-screen .quote-grid-item { background-color: var(--white); border-radius: var(--border-radius); padding: 15px; box-shadow: var(--box-shadow); font-size: 14px; line-height: 1.4; cursor: pointer; display: flex; flex-direction: column; justify-content: space-between;}
        #explore-screen .quote-grid-item p { margin: 0 0 8px 0;}
        #explore-screen .quote-grid-item .author { font-style: italic; color: var(--text-light); font-size: 12px; text-align: right; margin-bottom: 8px;}
        #explore-screen .quote-grid-item .quote-actions { justify-content: flex-start !important; }

        #create-status-screen { background-color: var(--medium-gray); flex-direction: column; justify-content: space-between; }
        body.dark-theme #create-status-screen { background-color: var(--dark-bg); }
        #create-status-screen .create-header { display: flex; justify-content: space-between; align-items: center; padding: 10px 15px; background-color: var(--white); border-bottom: 1px solid var(--medium-gray); }
        #create-status-screen .create-header h3 { margin:0; }
        #create-status-screen .create-header .action-btn { background: none; border: none; color: var(--primary-purple); font-size: 16px; font-weight: 500; padding: 5px 10px; }
        #create-status-screen .create-header .action-btn.save { color: var(--accent-color); }
        #create-status-screen .preview-canvas { flex-grow: 1; background: linear-gradient(135deg, #8BC6EC 0%, #9599E2 100%); margin: 15px; border-radius: var(--border-radius); display: flex; justify-content: center; align-items: center; text-align: center; color: var(--white); font-size: 20px; padding: 20px; box-shadow: inset 0 0 10px rgba(0,0,0,0.1); min-height: 200px; position: relative; overflow: hidden; }
        #create-status-screen .preview-canvas-text { font-family: 'Poppins', sans-serif; word-break: break-word; width: 100%; height: 100%; display: flex; justify-content: center; align-items: center; padding:10px; box-sizing: border-box; }
        #create-status-screen .editor-toolbar { display: flex; justify-content: space-around; background-color: var(--white); padding: 10px 0; border-top: 1px solid var(--medium-gray); }
        #create-status-screen .tool-item { display: flex; flex-direction: column; align-items: center; color: var(--text-light); cursor: pointer; font-size: 12px; padding: 5px 10px; flex: 1; }
        #create-status-screen .tool-item i { font-size: 20px; margin-bottom: 3px; }
        #create-status-screen .tool-item.active { color: var(--primary-purple); background: linear-gradient(to top, var(--light-purple) 0%, transparent 70%); border-radius: 5px; }
        .sub-tool-panel { display: none; padding: 10px; background-color: #f0f0f0; border-top: 1px solid #ccc; }
        body.dark-theme .sub-tool-panel { background-color: #444; border-top-color: #555; }
        .sub-tool-panel.active { display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; }
        .sub-tool-panel button, .sub-tool-panel input[type="color"] { margin: 5px; }
        .font-option { padding: 5px 10px; border: 1px solid #ccc; border-radius: 5px; cursor: pointer;}
        .emoji-option { font-size: 24px; cursor: pointer; padding: 5px;}

        #favorites-screen { background-color: var(--light-purple); }
        #favorites-screen .favorites-list { padding: 20px; }
        #favorites-screen #no-favorites-message { text-align: center; color: var(--text-light); font-size: 18px; margin-top: 50px; }
        #favorites-screen .favorite-item { position: relative; }
        #favorites-screen .favorite-item .quote-text { font-size: 16px; line-height: 1.5; margin-bottom: 8px; }
        #favorites-screen .favorite-item .quote-author { font-size: 13px; color: var(--text-light); font-style: italic; margin-bottom: 10px; text-align: right; }
        #favorites-screen .favorite-item .actions { display: flex; justify-content: flex-end; align-items: center; gap: 20px; margin-top: 10px; }
        #favorites-screen .favorite-item .actions i { font-size: 18px; color: var(--text-light); cursor: pointer; }
        #favorites-screen .favorite-item .actions i:hover { color: var(--primary-purple); }
        #favorites-screen .favorite-item .actions .fa-heart { color: var(--pastel-pink); }
        #favorites-screen .favorite-item .category-tag { display: inline-block; background-color: var(--light-purple); color: var(--dark-purple); padding: 3px 8px; border-radius: 5px; font-size: 12px; margin-bottom: 10px; }

        #settings-screen .settings-group { margin-bottom: 20px; background-color: var(--white); border-radius: var(--border-radius); box-shadow: var(--box-shadow); overflow: hidden; }
        #settings-screen .settings-group:first-child { margin-top:0; }
        #settings-screen .settings-item { display: flex; justify-content: space-between; align-items: center; padding: 15px; border-bottom: 1px solid var(--light-gray); cursor: pointer; }
        #settings-screen .settings-item:last-child { border-bottom: none; }
        #settings-screen .settings-item:hover { background-color: #f9f9f9; }
        body.dark-theme #settings-screen .settings-item:hover { background-color: #333; }
        #settings-screen .settings-item i.leading-icon { margin-right: 15px; color: var(--primary-purple); font-size: 18px; width: 20px; text-align: center; }
        #settings-screen .settings-item .text-content { flex-grow: 1; }
        #settings-screen .settings-item .text-content span { font-size: 16px; }
        #settings-screen .settings-item .text-content p { font-size: 12px; color: var(--text-light); margin: 2px 0 0 0; }
        #settings-screen .settings-item .action-element .toggle-switch { position: relative; display: inline-block; width: 44px; height: 24px; }
        #settings-screen .settings-item .action-element .toggle-switch input { opacity: 0; width: 0; height: 0; }
        #settings-screen .settings-item .action-element .slider { position: absolute; cursor: pointer; top: 0; left: 0; right: 0; bottom: 0; background-color: var(--medium-gray); transition: .4s; border-radius: 24px; }
        #settings-screen .settings-item .action-element .slider:before { position: absolute; content: ""; height: 18px; width: 18px; left: 3px; bottom: 3px; background-color: white; transition: .4s; border-radius: 50%; }
        #settings-screen .settings-item .action-element input:checked + .slider { background-color: var(--primary-purple); }
        #settings-screen .settings-item .action-element input:checked + .slider:before { transform: translateX(20px); }
        #settings-screen .settings-item .action-element .chevron { color: var(--text-light); font-size: 16px; }

        #remove-ads-screen { background: linear-gradient(135deg, var(--light-purple), var(--pastel-pink)); justify-content: center; align-items: center; text-align: center; padding: 20px; transition: background 0.3s; }
        body.dark-theme #remove-ads-screen { background: linear-gradient(135deg, var(--dark-light-purple), var(--dark-primary-purple)); }
        #remove-ads-screen .purchase-card { background-color: var(--white); border-radius: 20px; padding: 30px 25px; box-shadow: 0 10px 30px rgba(0,0,0,0.15); max-width: 350px; width: 100%; position: relative; }
        #remove-ads-screen .close-btn { position: absolute; top: 15px; left: 15px; background: none; border: none; font-size: 20px; color: var(--text-light); }
        #remove-ads-screen h2 { font-size: 26px; color: var(--dark-purple); margin-bottom: 10px; }
        #remove-ads-screen .price { font-size: 36px; font-weight: 700; color: var(--accent-color); margin-bottom: 20px; }
        #remove-ads-screen .price span { font-size:16px; font-weight:normal; color:var(--text-light) }
        #remove-ads-screen .benefits-list { list-style: none; padding: 0; margin-bottom: 30px; text-align: left; }
        #remove-ads-screen .benefits-list li { margin-bottom: 10px; font-size: 16px; color: var(--text-light); display: flex; align-items: center; }
        #remove-ads-screen .benefits-list li i { color: var(--primary-purple); margin-right: 10px; font-size: 18px; width: 20px; }
        #remove-ads-screen .buy-now-button { width: 100%; padding: 15px; font-size: 18px; background-color: var(--accent-color); margin-bottom: 15px; }
        #remove-ads-screen .restore-purchase { color: var(--primary-purple); font-size: 14px; text-decoration: none; cursor: pointer; }
        #remove-ads-screen .restore-purchase:hover { text-decoration: underline; }

        .bottom-sheet-overlay { position: fixed; top: 0; left: 0; right: 0; bottom: 0; background-color: rgba(0,0,0,0.4); z-index: 1001; display: none; }
        .bottom-sheet-overlay.active { display: block; }
        #quote-detail-bottom-sheet { position: fixed; bottom: 0; left: 0; right: 0; background-color: var(--white); border-top-left-radius: 20px; border-top-right-radius: 20px; padding: 20px; padding-top: 45px; box-shadow: 0 -5px 20px rgba(0,0,0,0.15); z-index: 1002; transform: translateY(100%); transition: transform 0.3s ease-in-out, background-color 0.3s; max-height: 80vh; overflow-y: auto; }
        #quote-detail-bottom-sheet.active { transform: translateY(0); }
        #quote-detail-bottom-sheet .close-bs-btn { position: absolute; top: 15px; right: 15px; font-size: 22px; color: var(--text-light); background: none; border: none; padding: 5px; }
        #quote-detail-bottom-sheet .quote-full-text { font-size: 18px; line-height: 1.6; margin-bottom: 10px; text-align: center; }
        #quote-detail-bottom-sheet .quote-full-author { font-size: 15px; color: var(--text-light); font-style: italic; text-align: center; margin-bottom: 25px; }
        #quote-detail-bottom-sheet .actions-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 15px; }
        #quote-detail-bottom-sheet .action-button { display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 12px; background-color: var(--light-purple); color: var(--dark-purple); border-radius: var(--border-radius); font-size: 14px; font-weight: 500; text-align: center; cursor: pointer; transition: background-color 0.2s ease; }
        #quote-detail-bottom-sheet .action-button:hover { background-color: var(--primary-purple); color: var(--text-on-purple); }
        #quote-detail-bottom-sheet .action-button i { font-size: 20px; margin-bottom: 5px; }

        .toast-notification { position: fixed; bottom: 80px; left: 50%; transform: translateX(-50%); background-color: rgba(0,0,0,0.75); color: white; padding: 10px 20px; border-radius: 20px; font-size: 14px; z-index: 2000; opacity: 0; transition: opacity 0.3s ease, bottom 0.3s ease; visibility: hidden; }
        .toast-notification.show { opacity: 1; bottom: 90px; visibility: visible; }
        body.dark-theme .toast-notification { background-color: rgba(220,220,220,0.85); color: #333; }

    </style>
</head>
<body>
    <!-- HTML Structure (Identical to the previous version) -->
    <div id="app-container">
        <div id="splash-screen" class="app-screen no-bottom-padding">
            <div class="logo" data-translate-key="appName">Quotezy</div>
            <div class="tagline" data-translate-key="appTagline">Provide By Great</div>
        </div>
        <div id="onboarding-screen-1" class="app-screen no-bottom-padding">
            <div class="onboarding-content">
                <div class="illustration"><i class="fas fa-book-reader"></i></div>
                <h2 data-translate-key="onboarding1Title">Find Your Daily Spark</h2>
                <p data-translate-key="onboarding1Desc">Discover inspiring quotes tailored to your mood and aspirations every day.</p>
                <div class="nav-dots">
                    <span class="dot active" data-slide="1"></span>
                    <span class="dot" data-slide="2"></span>
                    <span class="dot" data-slide="3"></span>
                </div>
                <button class="next-button" onclick="nextOnboardingSlide(1)" data-translate-key="nextButton">Next</button>
            </div>
        </div>
         <!-- Onboarding Slide 2 (Example) -->
        <div id="onboarding-screen-2" class="app-screen no-bottom-padding" style="background-color: var(--light-purple); justify-content: center; align-items: center; text-align: center; padding: 30px 20px;">
            <div class="onboarding-content">
                <div class="illustration" style="font-size: 50px; color: var(--primary-purple);"><i class="fas fa-mobile-alt"></i></div>
                <h2 data-translate-key="onboarding2Title">Quotes That Speak to You</h2>
                <p data-translate-key="onboarding2Desc">Customize your feed and explore diverse categories.</p>
                 <div class="nav-dots">
                    <span class="dot" data-slide="1"></span>
                    <span class="dot active" data-slide="2"></span>
                    <span class="dot" data-slide="3"></span>
                </div>
                <button class="next-button" onclick="nextOnboardingSlide(2)" data-translate-key="nextButton">Next</button>
            </div>
        </div>
        <!-- Onboarding Slide 3 (Example) -->
        <div id="onboarding-screen-3" class="app-screen no-bottom-padding" style="background-color: var(--light-purple); justify-content: center; align-items: center; text-align: center; padding: 30px 20px;">
            <div class="onboarding-content">
                <div class="illustration" style="font-size: 50px; color: var(--primary-purple);"><i class="fas fa-share-alt"></i></div>
                <h2 data-translate-key="onboarding3Title">Share. Save. Feel Inspired.</h2>
                <p data-translate-key="onboarding3Desc">Spread positivity and keep your favorite quotes handy.</p>
                 <div class="nav-dots">
                    <span class="dot" data-slide="1"></span>
                    <span class="dot" data-slide="2"></span>
                    <span class="dot active" data-slide="3"></span>
                </div>
                <button class="next-button" onclick="finishOnboarding()" data-translate-key="getStartedButton">Get Started</button>
            </div>
        </div>

        <div id="language-selection-screen" class="app-screen no-bottom-padding">
            <div class="screen-header" data-translate-key="selectLanguageTitle">Select Language</div>
            <div class="screen-content">
                <ul class="language-list">
                    <li class="language-item" onclick="selectLanguage(this, 'en')"><span><span class="flag">🇺🇸</span> English</span><i class="fas fa-check checkmark"></i></li>
                    <li class="language-item" onclick="selectLanguage(this, 'es')"><span><span class="flag">🇪🇸</span> Español (Spanish)</span><i class="fas fa-check checkmark"></i></li>
                    <li class="language-item" onclick="selectLanguage(this, 'hi')"><span><span class="flag">🇮🇳</span> हिन्दी (Hindi)</span><i class="fas fa-check checkmark"></i></li>
                    <li class="language-item" onclick="selectLanguage(this, 'fr')"><span><span class="flag">🇫🇷</span> Français (French)</span><i class="fas fa-check checkmark"></i></li>
                </ul>
            </div>
            <div class="continue-button-container"><button class="continue-button" onclick="completeLanguageSelection()" data-translate-key="continueButton">Continue</button></div>
        </div>
        <div id="home-screen" class="app-screen">
            <div class="home-screen-gradient-bg">
                <div class="home-header-greeting">
                    <h1 data-translate-key="homeGreeting">Good Morning!</h1>
                </div>
                <div class="screen-content" style="padding-top:0;">
                    <button class="create-status-button" onclick="showScreen('create-status-screen', false)">
                        <i class="fas fa-plus"></i> <span data-translate-key="createStatusBtn">Create Status</span>
                    </button>
                    <div class="quote-card card" id="qotdCard" data-quote-id="qotd_placeholder">
                        <h3 data-translate-key="qotdTitle">Quote of the day!</h3>
                        <p class="quote-text" id="qotdText"></p>
                        <p class="quote-author" id="qotdAuthor"></p>
                        <div class="quote-actions">
                            <i class="fas fa-heart" onclick="toggleFavorite(this.parentElement.parentElement.dataset.quoteId, this)"></i>
                            <i class="fas fa-copy" onclick="copyQuoteContent(this.parentElement.parentElement.dataset.quoteId)"></i>
                        </div>
                    </div>
                    <div class="quote-card card" id="trendingNowCard" data-quote-id="q_beOfValue">
                         <h3 data-translate-key="trendingNowTitle">Trending Now</h3>
                        <p class="quote-text" id="trendingNowText"></p>
                        <p class="quote-author" id="trendingNowAuthor"></p>
                         <div class="quote-meta">
                            <span class="category" id="trendingNowCategory" data-translate-key="categoryMotivation">Motivation</span>
                            <span class="likes"><i class="fas fa-heart"></i></span>
                        </div>
                        <div class="quote-actions">
                            <i class="fas fa-heart" onclick="toggleFavorite('q_beOfValue', this)"></i>
                            <i class="fas fa-copy" onclick="copyQuoteContent('q_beOfValue')"></i>
                        </div>
                    </div>
                    <h2 class="section-title" data-translate-key="exploreCategoriesTitle">Explore Categories</h2>
                    <div class="explore-preview">
                        <div class="explore-preview-item" onclick="exploreByCategory('Motivation')" data-translate-key="categoryMotivation">Motivation</div>
                        <div class="explore-preview-item" onclick="exploreByCategory('Love')" data-translate-key="categoryLove">Love</div>
                        <div class="explore-preview-item" onclick="exploreByCategory('Success')" data-translate-key="categorySuccess">Success</div>
                        <div class="explore-preview-item" onclick="exploreByCategory('Wisdom')" data-translate-key="categoryWisdom">Wisdom</div>
                         <div class="explore-preview-item" onclick="exploreByCategory('Humor')" data-translate-key="categoryHumor">Humor</div>
                    </div>
                </div>
            </div>
        </div>
        <div id="explore-screen" class="app-screen">
            <div class="explore-header"><h1 data-translate-key="exploreTitle">Explore</h1></div>
            <div class="filters">
                <button class="filter-btn active" onclick="applyExploreFilter(this, 'all')" data-translate-key="filterAll">All</button>
                <button class="filter-btn" onclick="applyExploreFilter(this, 'category', 'Success')" data-translate-key="categorySuccess">Success</button>
                <button class="filter-btn" onclick="applyExploreFilter(this, 'category', 'Love')" data-translate-key="categoryLove">Love</button>
                <button class="filter-btn" onclick="applyExploreFilter(this, 'category', 'Motivation')" data-translate-key="categoryMotivation">Motivation</button>
                <button class="filter-btn" onclick="applyExploreFilter(this, 'category', 'Wisdom')" data-translate-key="categoryWisdom">Wisdom</button>
                <button class="filter-btn" onclick="applyExploreFilter(this, 'category', 'Humor')" data-translate-key="categoryHumor">Humor</button>
            </div>
            <div class="screen-content"><div class="quote-grid" id="exploreQuoteGrid"></div></div>
        </div>
        <div id="create-status-screen" class="app-screen no-bottom-padding">
            <div class="create-header">
                <button class="action-btn" onclick="showScreen('home-screen', true)" data-translate-key="cancelButton">Cancel</button>
                <h3 data-translate-key="createStatusTitle">Create Status</h3>
                <button class="action-btn save" onclick="saveStatusAsImage()" data-translate-key="saveButton">Save</button>
            </div>
            <div id="previewCanvas" class="preview-canvas">
                <span id="previewCanvasText" contenteditable="true" data-placeholder-key="statusPlaceholder">Type your status...</span>
            </div>
            <div id="subToolsContainer"></div>
            <div class="editor-toolbar">
                <div class="tool-item" onclick="toggleSubTool('background')"><i class="fas fa-image"></i> <span data-translate-key="toolBackground">Background</span></div>
                <div class="tool-item" onclick="toggleSubTool('text')"><i class="fas fa-font"></i> <span data-translate-key="toolText">Text</span></div>
                <div class="tool-item" onclick="toggleSubTool('font')"><i class="fas fa-text-height"></i> <span data-translate-key="toolFont">Font</span></div>
                <div class="tool-item" onclick="toggleSubTool('emoji')"><i class="fas fa-smile"></i> <span data-translate-key="toolEmoji">Emoji</span></div>
                <div class="tool-item" onclick="toggleSubTool('color')"><i class="fas fa-palette"></i> <span data-translate-key="toolColor">Color</span></div>
            </div>
        </div>
        <div id="favorites-screen" class="app-screen">
            <div class="app-main-header"><h1 data-translate-key="favoritesTitle">Favourites</h1></div>
            <div class="favorites-list screen-content" id="favoritesListContainer">
                <p id="no-favorites-message" data-translate-key="noFavoritesMsg">No favorites yet. Start exploring!</p>
            </div>
        </div>
        <div id="settings-screen" class="app-screen">
            <div class="app-main-header"><h1 data-translate-key="settingsTitle">Settings</h1></div>
            <div class="screen-content">
                <div class="settings-group">
                    <div class="settings-item">
                        <i class="fas fa-palette leading-icon"></i>
                        <div class="text-content"><span data-translate-key="settingsTheme">Theme</span><p data-translate-key="settingsThemeDesc">Light / Dark Mode</p></div>
                        <div class="action-element"><label class="toggle-switch"><input type="checkbox" id="themeToggleSwitch"><span class="slider"></span></label></div>
                    </div>
                    <div class="settings-item" onclick="showScreen('language-selection-screen', false)">
                        <i class="fas fa-language leading-icon"></i>
                         <div class="text-content"><span data-translate-key="settingsLanguage">Language</span><p id="currentLanguageSetting" data-translate-key="settingsLangEnglish">English</p></div>
                        <div class="action-element"><i class="fas fa-chevron-right chevron"></i></div>
                    </div>
                    <div class="settings-item">
                        <i class="fas fa-bell leading-icon"></i>
                        <div class="text-content"><span data-translate-key="settingsNotifications">Daily Notifications</span><p data-translate-key="settingsNotificationsDesc">Get your daily dose of inspiration</p></div>
                        <div class="action-element"><label class="toggle-switch"><input type="checkbox" checked><span class="slider"></span></label></div>
                    </div>
                </div>
                <div class="settings-group">
                     <div class="settings-item" onclick="showScreen('remove-ads-screen', false)">
                        <i class="fas fa-ad leading-icon"></i>
                        <div class="text-content"><span data-translate-key="settingsRemoveAds">Remove Ads</span><p data-translate-key="settingsRemoveAdsDesc">Enjoy an ad-free experience</p></div>
                        <div class="action-element"><i class="fas fa-chevron-right chevron"></i></div>
                    </div>
                    <div class="settings-item">
                        <i class="fas fa-info-circle leading-icon"></i>
                        <div class="text-content"><span data-translate-key="settingsAbout">About Quotezy</span><p>Version 1.0.5</p></div>
                    </div>
                     <a href="mailto:adilahamad6032005@gmail.com" class="settings-item" style="text-decoration: none; color: inherit;">
                        <i class="fas fa-headset leading-icon"></i>
                        <div class="text-content"><span data-translate-key="settingsSupport">Support & Feedback</span><p data-translate-key="settingsSupportDesc">Contact us or report an issue</p></div>
                         <div class="action-element"><i class="fas fa-chevron-right chevron"></i></div>
                    </a>
                </div>
            </div>
        </div>
        <div id="remove-ads-screen" class="app-screen no-bottom-padding">
            <div class="purchase-card">
                <button class="close-btn" onclick="showScreen('settings-screen', true)"><i class="fas fa-arrow-left"></i></button>
                <h2 data-translate-key="removeAdsTitle">Remove Ads</h2>
                <div class="price">₹49 <span data-translate-key="perMonth">/month</span></div>
                <ul class="benefits-list">
                    <li data-translate-key="benefitAdFree"><i class="fas fa-check-circle"></i> Enjoy an ad-free experience</li>
                    <li data-translate-key="benefitFaster"><i class="fas fa-check-circle"></i> Faster app performance</li>
                    <li data-translate-key="benefitSupportDev"><i class="fas fa-check-circle"></i> Support future development</li>
                    <li data-translate-key="benefitOneTimePay"><i class="fas fa-check-circle"></i> Easy monthly subscription</li>
                </ul>
                <a href="upi://pay?pa=821827473@ybl&pn=Asib Ahamad&tn=for Quotezy Premium&am=49&cu=INR" target="_blank" class="button buy-now-button" data-translate-key="buyNowButton">Buy Now</a>
                <a href="#" class="restore-purchase" data-translate-key="restorePurchases">Restore Purchases</a>
            </div>
        </div>
        <div class="bottom-sheet-overlay" id="bottomSheetOverlay" onclick="closeQuoteDetail()"></div>
        <div id="quote-detail-bottom-sheet">
            <button class="close-bs-btn" onclick="closeQuoteDetail()"><i class="fas fa-times"></i></button>
            <p id="bsQuoteText" class="quote-full-text"></p>
            <p id="bsQuoteAuthor" class="quote-full-author"></p>
            <div class="actions-grid">
                <div class="action-button" onclick="copyFromBottomSheet()"><i class="fas fa-copy"></i> <span data-translate-key="copyButton">Copy</span></div>
                <div class="action-button" onclick="favoriteFromBottomSheet()"><i class="fas fa-heart"></i> <span data-translate-key="favoriteButton">Favorite</span></div>
                <div class="action-button" onclick="shareFromBottomSheet()"><i class="fas fa-share-alt"></i> <span data-translate-key="shareButton">Share</span></div>
                <div class="action-button" onclick="createImageFromBottomSheet()"><i class="fas fa-image"></i> <span data-translate-key="createImageButton">Create Image</span></div>
            </div>
        </div>
        <div id="bottom-nav-template" style="display: none;">
            <div class="nav-item" data-screen="home-screen"><i class="fas fa-home"></i> <span data-translate-key="navHome">Home</span></div>
            <div class="nav-item" data-screen="explore-screen"><i class="fas fa-search"></i> <span data-translate-key="navExplore">Explore</span></div>
            <div class="nav-item" data-screen="favorites-screen"><i class="fas fa-heart"></i> <span data-translate-key="navFavorites">Favourites</span></div>
            <div class="nav-item" data-screen="settings-screen"><i class="fas fa-cog"></i> <span data-translate-key="navSettings">Settings</span></div>
        </div>
        <div id="toast-container" class="toast-notification"></div>
    </div>

    <script>
        // --- State & Config ---
        let currentScreenId = null;
        let selectedLanguage = 'en';
        const screensWithNav = ['home-screen', 'explore-screen', 'favorites-screen', 'settings-screen'];
        let bottomNavElement = null;
        let favoriteQuoteIds = []; // Will be loaded from localStorage
        let currentOnboardingSlide = 1;
        const totalOnboardingSlides = 3; // Define total number of onboarding slides

        // --- UI Text Translations Data ---
        const uiTranslations = {
            'en': { /* ... All UI keys ... */
                appName: "Quotezy", appTagline: "Provide By Great",
                onboarding1Title: "Find Your Daily Spark", onboarding1Desc: "Discover inspiring quotes tailored to your mood and aspirations every day.",
                onboarding2Title: "Quotes That Speak to You", onboarding2Desc: "Customize your feed and explore diverse categories.",
                onboarding3Title: "Share. Save. Feel Inspired.", onboarding3Desc: "Spread positivity and keep your favorite quotes handy.",
                getStartedButton: "Get Started",
                nextButton: "Next", selectLanguageTitle: "Select Language", continueButton: "Continue", homeGreeting: "Good Morning!", createStatusBtn: "Create Status", qotdTitle: "Quote of the day!", trendingNowTitle: "Trending Now", exploreCategoriesTitle: "Explore Categories", categoryMotivation: "Motivation", categoryLove: "Love", categoryWisdom: "Wisdom", categorySuccess: "Success", categoryHumor: "Humor", exploreTitle: "Explore", filterTrending: "Trending", filterMoodHappy: "Mood: Happy", filterCatLife: "Category: Life", filterAll: "All", cancelButton: "Cancel", createStatusTitle: "Create Status", saveButton: "Save", statusPlaceholder: "Type your status...", toolBackground: "Background", toolText: "Text", toolFont: "Font", toolEmoji: "Emoji", toolColor: "Color", favoritesTitle: "Favourites", noFavoritesMsg: "No favorites yet. Start exploring!", settingsTitle: "Settings", settingsTheme: "Theme", settingsThemeDesc: "Light / Dark Mode", settingsLanguage: "Language", settingsLangEnglish: "English", settingsLangSpanish: "Spanish", settingsLangHindi: "Hindi", settingsNotifications: "Daily Notifications", settingsNotificationsDesc: "Get your daily dose of inspiration", settingsRemoveAds: "Remove Ads", settingsRemoveAdsDesc: "Enjoy an ad-free experience", settingsAbout: "About Quotezy", settingsSupport: "Support & Feedback", settingsSupportDesc: "Contact us or report an issue", removeAdsTitle: "Remove Ads", perMonth: "/month", benefitAdFree: "Enjoy an ad-free experience", benefitFaster: "Faster app performance", benefitSupportDev: "Support future development", benefitOneTimePay: "Easy monthly subscription", buyNowButton: "Buy Now", restorePurchases: "Restore Purchases", copyButton: "Copy", favoriteButton: "Favorite", shareButton: "Share", createImageButton: "Create Image", navHome: "Home", navExplore: "Explore", navFavorites: "Favourites", navSettings: "Settings", alertCopied: "Copied to clipboard!", alertFavorited: "Added to favorites!", alertUnfavorited: "Removed from favorites!", alertNotImplemented: "Feature not yet implemented.", alertExploreFilter: "Filtering by: ", alertStatusSaved: "Status image download started!", alertStatusEmpty: "Please enter some text for your status."
            },
            'es': { /* ... Spanish UI keys ... */
                appName: "Quotezy", appTagline: "Crea Tu Ambiente",
                onboarding1Title: "Encuentra Tu Chispa Diaria", onboarding1Desc: "Descubre citas inspiradoras adaptadas a tu estado de ánimo y aspiraciones cada día.",
                onboarding2Title: "Citas Que Te Hablan", onboarding2Desc: "Personaliza tu feed y explora diversas categorías.",
                onboarding3Title: "Comparte. Guarda. Siéntete Inspirado.", onboarding3Desc: "Difunde positividad y ten tus citas favoritas a mano.",
                getStartedButton: "Empezar",
                nextButton: "Siguiente", selectLanguageTitle: "Seleccionar Idioma", continueButton: "Continuar", homeGreeting: "¡Buenos Días!", createStatusBtn: "Crear Estado", qotdTitle: "¡Cita del día!", trendingNowTitle: "Tendencias Ahora", exploreCategoriesTitle: "Explorar Categorías", categoryMotivation: "Motivación", categoryLove: "Amor", categoryWisdom: "Sabiduría", categorySuccess: "Éxito", categoryHumor: "Humor", exploreTitle: "Explorar", filterTrending: "Tendencias", filterMoodHappy: "Ánimo: Feliz", filterCatLife: "Categoría: Vida", filterAll: "Todo", cancelButton: "Cancelar", createStatusTitle: "Crear Estado", saveButton: "Guardar", statusPlaceholder: "Escribe tu estado...", toolBackground: "Fondo", toolText: "Texto", toolFont: "Fuente", toolEmoji: "Emoji", toolColor: "Color", favoritesTitle: "Favoritos", noFavoritesMsg: "Aún no hay favoritos. ¡Empieza a explorar!", settingsTitle: "Ajustes", settingsTheme: "Tema", settingsThemeDesc: "Modo Claro / Oscuro", settingsLanguage: "Idioma", settingsLangEnglish: "Inglés", settingsLangSpanish: "Español", settingsLangHindi: "Hindi", settingsNotifications: "Notificaciones Diarias", settingsNotificationsDesc: "Recibe tu dosis diaria de inspiración", settingsRemoveAds: "Eliminar Anuncios", settingsRemoveAdsDesc: "Disfruta de una experiencia sin anuncios", settingsAbout: "Acerca de Quotezy", settingsSupport: "Soporte y Comentarios", settingsSupportDesc: "Contáctanos o reporta un problema", removeAdsTitle: "Eliminar Anuncios", perMonth: "/mes", benefitAdFree: "Disfruta una experiencia sin anuncios", benefitFaster: "Rendimiento más rápido", benefitSupportDev: "Apoya el desarrollo futuro", benefitOneTimePay: "Suscripción mensual fácil", buyNowButton: "Comprar Ahora", restorePurchases: "Restaurar Compras", copyButton: "Copiar", favoriteButton: "Favorito", shareButton: "Compartir", createImageButton: "Crear Imagen", navHome: "Inicio", navExplore: "Explorar", navFavorites: "Favoritos", navSettings: "Ajustes", alertCopied: "¡Copiado al portapapeles!", alertFavorited: "¡Añadido a favoritos!", alertUnfavorited: "¡Eliminado de favoritos!", alertNotImplemented: "Función aún no implementada.", alertExploreFilter: "Filtrando por: ", alertStatusSaved: "¡Descarga de imagen de estado iniciada!", alertStatusEmpty: "Por favor ingresa texto para tu estado."
            },
            'hi': { /* ... Hindi UI keys ... */
                appName: "स्टेटसक्राफ्ट", appTagline: "अपनी वाइब बनाएं",
                onboarding1Title: "अपनी दैनिक चिंगारी ढूंढें", onboarding1Desc: "हर दिन अपने मूड और आकांक्षाओं के अनुरूप प्रेरक उद्धरण खोजें।",
                onboarding2Title: "उद्धरण जो आपसे बात करते हैं", onboarding2Desc: "अपनी फ़ीड को अनुकूलित करें और विविध श्रेणियों का अन्वेषण करें।",
                onboarding3Title: "शेयर करें। सहेजें। प्रेरित महसूस करें।", onboarding3Desc: "सकारात्मकता फैलाएं और अपने पसंदीदा उद्धरण संभाल कर रखें।",
                getStartedButton: "शुरू करें",
                nextButton: "अगला", selectLanguageTitle: "भाषा चुनें", continueButton: "जारी रखें", homeGreeting: "सुप्रभात!", createStatusBtn: "स्टेटस बनाएं", qotdTitle: "आज का विचार!", trendingNowTitle: "अभी ट्रेंडिंग में", exploreCategoriesTitle: "श्रेणियाँ एक्सप्लोर करें", categoryMotivation: "प्रेरणा", categoryLove: "प्यार", categoryWisdom: "ज्ञान", categorySuccess: "सफलता", categoryHumor: "हास्य", exploreTitle: "एक्सप्लोर करें", filterTrending: "ट्रेंडिंग", filterMoodHappy: "मूड: खुश", filterCatLife: "श्रेणी: जीवन", filterAll: "सभी", cancelButton: "रद्द करें", createStatusTitle: "स्टेटस बनाएं", saveButton: "सहेजें", statusPlaceholder: "अपना स्टेटस टाइप करें...", toolBackground: "पृष्ठभूमि", toolText: "टेक्स्ट", toolFont: "फ़ॉन्ट", toolEmoji: "इमोजी", toolColor: "रंग", favoritesTitle: "पसंदीदा", noFavoritesMsg: "अभी तक कोई पसंदीदा नहीं। एक्सप्लोर करना शुरू करें!", settingsTitle: "सेटिंग्स", settingsTheme: "थीम", settingsThemeDesc: "लाइट / डार्क मोड", settingsLanguage: "भाषा", settingsLangEnglish: "अंग्रेज़ी", settingsLangSpanish: "स्पेनिश", settingsLangHindi: "हिन्दी", settingsNotifications: "दैनिक सूचनाएं", settingsNotificationsDesc: "अपनी दैनिक प्रेरणा पाएं", settingsRemoveAds: "विज्ञापन हटाएं", settingsRemoveAdsDesc: "विज्ञापन-मुक्त अनुभव का आनंद लें", settingsAbout: "स्टेटसक्राफ्ट के बारे में", settingsSupport: "सहायता और प्रतिक्रिया", settingsSupportDesc: "हमसे संपर्क करें या कोई समस्या बताएं", removeAdsTitle: "विज्ञापन हटाएँ", perMonth: "/माह", benefitAdFree: "विज्ञापन-मुक्त अनुभव का आनंद लें", benefitFaster: "तेज़ ऐप प्रदर्शन", benefitSupportDev: "भविष्य के विकास का समर्थन करें", benefitOneTimePay: "आसान मासिक सदस्यता", buyNowButton: "अभी खरीदें", restorePurchases: "खरीदारी बहाल करें", copyButton: "कॉपी करें", favoriteButton: "पसंदीदा करें", shareButton: "शेयर करें", createImageButton: "छवि बनाएं", navHome: "होम", navExplore: "एक्सप्लोर", navFavorites: "पसंदीदा", navSettings: "सेटिंग्स", alertCopied: "क्लिपबोर्ड पर कॉपी किया गया!", alertFavorited: "पसंदीदा में जोड़ा गया!", alertUnfavorited: "पसंदीदा से हटाया गया!", alertNotImplemented: "सुविधा अभी लागू नहीं हुई है।", alertExploreFilter: "इसके द्वारा फ़िल्टर कर रहे हैं: ", alertStatusSaved: "स्टेटस छवि डाउनलोड शुरू हो गया है!", alertStatusEmpty: "कृपया अपने स्टेटस के लिए कुछ टेक्स्ट दर्ज करें।"
            }
        };

        // --- Quote Data & Translations (same extensive list as before) ---
        const qotdPool = ['q_doGreatWork', 's2', 'l8', 'm2', 'mx2', 'mx4', 'mx12', 'mx14', 'mx16', 'mx20']; // Example pool for QOTD

        const allQuotes = { /* ... Identical to previous version's allQuotes ... */
            'q_doGreatWork': { category: 'Motivation' }, 'q_beOfValue': { category: 'Motivation' },
            's1': { category: 'Success' }, 's2': { category: 'Success' }, 's3': { category: 'Success' }, 's4': { category: 'Success' }, 's5': { category: 'Success' }, 's6': { category: 'Success' }, 's7': { category: 'Success' }, 's8': { category: 'Success' }, 's9': { category: 'Success' }, 's10': { category: 'Success' },
            'l1': { category: 'Love' }, 'l2': { category: 'Love' }, 'l3': { category: 'Love' }, 'l4': { category: 'Love' }, 'l5': { category: 'Love' }, 'l6': { category: 'Love' }, 'l7': { category: 'Love' }, 'l8': { category: 'Love' }, 'l9': { category: 'Love' }, 'l10': { category: 'Love' },
            'm1': { category: 'Motivation' }, 'm2': { category: 'Motivation' }, 'm3': { category: 'Motivation' }, 'm4': { category: 'Motivation' }, 'm5': { category: 'Motivation' }, 'm6': { category: 'Motivation' }, 'm7': { category: 'Motivation' }, 'm8': { category: 'Motivation' }, 'm9': { category: 'Motivation' }, 'm10': { category: 'Motivation' },
            'mx1': { category: 'Wisdom' }, 'mx2': { category: 'Motivation' }, 'mx3': { category: 'Wisdom' }, 'mx4': { category: 'Motivation' }, 'mx5': { category: 'Motivation' }, 'mx6': { category: 'Love' }, 'mx7': { category: 'Wisdom' }, 'mx8': { category: 'Motivation' }, 'mx9': { category: 'Motivation' }, 'mx10': { category: 'Success' }, 'mx11': { category: 'Motivation' }, 'mx12': { category: 'Success' }, 'mx13': { category: 'Wisdom' }, 'mx14': { category: 'Motivation' }, 'mx15': { category: 'Motivation' }, 'mx16': { category: 'Motivation' }, 'mx17': { category: 'Humor' }, 'mx18': { category: 'Motivation' }, 'mx19': { category: 'Love' }, 'mx20': { category: 'Wisdom' }
        };
        const quoteContentTranslations = { /* ... Identical to previous version's quoteContentTranslations ... */
            'en': {
                'q_doGreatWork': { text: "The only way to do great work is to love what you do.", author: "Steve Jobs" }, 'q_beOfValue': { text: "Strive not to be a success, but rather to be of value.", author: "Albert Einstein" },
                's1': { text: "Success is not what you achieve, but the struggle you endure to achieve it.", author: "Unknown" }, 's2': { text: "Success is not final, failure is not fatal: It is the courage to continue that counts.", author: "Winston Churchill" }, 's3': { text: "The destination will be reached, even if by wandering; lost are those who never left home.", author: "Unknown" }, 's4': { text: "The road to success and the road to failure are almost exactly the same.", author: "Colin R. Davis" }, 's5': { text: "The secret to success is: hard work, perseverance, and never giving up.", author: "Unknown" }, 's6': { text: "Success usually comes to those who are too busy to be looking for it.", author: "Henry David Thoreau" }, 's7': { text: "Winners don't do different things, they do things differently.", author: "Shiv Khera" }, 's8': { text: "Don’t chase success, chase excellence and success will follow.", author: "Unknown (Often attributed to 3 Idiots movie)" }, 's9': { text: "Success is the sum of small efforts, repeated day in and day out.", author: "Robert Collier" }, 's10': { text: "The secret of success is to do the common thing uncommonly well.", author: "John D. Rockefeller" },
                'l1': { text: "Love is not seen, it is felt.", author: "Unknown" }, 'l2': { text: "Love isn’t something you find. Love is something that finds you.", author: "Loretta Young" }, 'l3': { text: "Love is a flower that can bloom in any season.", author: "Unknown" }, 'l4': { text: "We are most alive when we’re in love.", author: "John Updike" }, 'l5': { text: "True love never ends, it just resides in memories.", author: "Unknown" }, 'l6': { text: "Love is composed of a single soul inhabiting two bodies.", author: "Aristotle" }, 'l7': { text: "In love, it's not about rising after falling, but walking together even after falling.", author: "Unknown" }, 'l8': { text: "The best thing to hold onto in life is each other.", author: "Audrey Hepburn" }, 'l9': { text: "Love is about giving unconditionally, otherwise it's just a transaction.", author: "Unknown" }, 'l10': { text: "Love doesn’t make the world go round. Love is what makes the ride worthwhile.", author: "Franklin P. Jones" },
                'm1': { text: "Until you try, you don't know what you can do.", author: "Unknown" }, 'm2': { text: "Believe you can and you’re halfway there.", author: "Theodore Roosevelt" }, 'm3': { text: "Give up only when there's no life left in your heart, otherwise one more try never hurts.", author: "Unknown" }, 'm4': { text: "Your limitation—it’s only your imagination.", author: "Unknown" }, 'm5': { text: "Struggle makes a person complete, not success.", author: "Unknown" }, 'm6': { text: "Push yourself, because no one else is going to do it for you.", author: "Unknown" }, 'm7': { text: "Only those who fight difficulties move forward in life.", author: "Unknown" }, 'm8': { text: "Dream big and dare to fail.", author: "Norman Vaughan" }, 'm9': { text: "If the path were easy, everyone would reach the destination.", author: "Unknown" }, 'm10': { text: "The harder you work for something, the greater you’ll feel when you achieve it.", author: "Unknown" },
                'mx1': { text: "He who fears is as good as dead.", author: "Sholay (Movie Dialogue)" }, 'mx2': { text: "If you want to shine like a sun, first burn like a sun.", author: "APJ Abdul Kalam" }, 'mx3': { text: "Time changes, circumstances change, only intentions should be strong.", author: "Unknown" }, 'mx4': { text: "You are never too old to set another goal or to dream a new dream.", author: "C.S. Lewis" }, 'mx5': { text: "Nothing is impossible, just courage is needed.", author: "Unknown" }, 'mx6': { text: "Do what you love, love what you do.", author: "Unknown" }, 'mx7': { text: "As long as you live, keep learning.", author: "Unknown" }, 'mx8': { text: "The only way to do great work is to love what you do.", author: "Steve Jobs" }, 'mx9': { text: "Change yourself, destiny will change itself.", author: "Unknown" }, 'mx10': { text: "Success is walking from failure to failure with no loss of enthusiasm.", author: "Winston Churchill" }, 'mx11': { text: "He who dreams and does not give up, makes history.", author: "Unknown" }, 'mx12': { text: "You miss 100% of the shots you don’t take.", author: "Wayne Gretzky" }, 'mx13': { text: "Difficulties exist only as long as you consider them difficult.", author: "Unknown" }, 'mx14': { text: "Don’t count the days, make the days count.", author: "Muhammad Ali" }, 'mx15': { text: "More important than the will to win is the courage to fight the fear of losing.", author: "Unknown" }, 'mx16': { text: "The future depends on what you do today.", author: "Mahatma Gandhi" }, 'mx17': { text: "If you want to fulfill your dreams, first complete your sleep.", author: "Unknown (Funny)" }, 'mx18': { text: "Strive not to be a success, but rather to be of value.", author: "Albert Einstein" }, 'mx19': { text: "He who lives for others, truly lives.", author: "Unknown" }, 'mx20': { text: "Life is 10% what happens to us and 90% how we react to it.", author: "Charles R. Swindoll"}
            },
            'es': { /* ... Spanish Translations ... */
                'q_doGreatWork': { text: "La única manera de hacer un gran trabajo es amar lo que haces.", author: "Steve Jobs" }, 'q_beOfValue': { text: "No te esfuerces por ser un éxito, sino por ser de valor.", author: "Albert Einstein" },
                's2': { text: "El éxito no es definitivo, el fracaso no es fatal: lo que cuenta es el coraje de continuar.", author: "Winston Churchill" }, 'l8': { text: "Lo mejor a lo que aferrarse en la vida es el uno al otro.", author: "Audrey Hepburn" }, 'm2': { text: "Cree que puedes y ya estás a medio camino.", author: "Theodore Roosevelt" }, 'mx2': { text: "Si quieres brillar como el sol, primero quema como el sol.", author: "APJ Abdul Kalam" },
             },
            'hi': { /* ... Hindi Translations ... */
                'q_doGreatWork': { text: "महान कार्य करने का एकमात्र तरीका यह है कि आप जो करते हैं उससे प्यार करें।", author: "स्टीव जॉब्स" }, 'q_beOfValue': { text: "सफलता का प्रयास न करें, बल्कि मूल्यवान बनने का प्रयास करें।", author: "अल्बर्ट आइंस्टीन" },
                's1': { text: "सफलता वह नहीं जो तुम्हें मिल जाए, बल्कि वह है जिसे पाने के लिए तुमने संघर्ष किया।", author: "अज्ञात" }, 's2': { text: "सफलता अंतिम नहीं है, असफलता घातक नहीं है: जारी रखने का साहस ही मायने रखता है।", author: "विंस्टन चर्चिल" }, 's3': { text: "मंजिल मिल ही जाएगी, भटकते ही सही, गुमराह तो वो हैं जो घर से निकले ही नहीं।", author: "अज्ञात" }, 's4': { text: "सफलता की राह और असफलता की राह लगभग एक जैसी ही होती हैं।", author: "कॉलिन आर. डेविस" }, 's5': { text: "कामयाबी का राज़ है: मेहनत, लगन और कभी हार न मानना।", author: "अज्ञात" }, 's6': { text: "सफलता आमतौर पर उन लोगों को मिलती है जो इसे खोजने में बहुत व्यस्त होते हैं।", author: "हेनरी डेविड थोरो" }, 's7': { text: "जीतने वाले अलग चीजें नहीं करते, वो चीजों को अलग तरह से करते हैं।", author: "शिव खेड़ा" }, 's8': { text: "सफलता का पीछा मत करो, उत्कृष्टता का पीछा करो और सफलता तुम्हारे पीछे आएगी।", author: "अज्ञात" }, 's9': { text: "सफलता छोटे-छोटे प्रयासों का योग है, जो रोज़ दोहराये जाते हैं।", author: "रॉबर्ट कोलियर" }, 's10': { text: "सफलता का रहस्य सामान्य काम को असामान्य रूप से अच्छी तरह से करना है।", author: "जॉन डी. रॉकफेलर" },
                'l1': { text: "प्यार देखा नहीं जाता, महसूस किया जाता है।", author: "अज्ञात" }, 'l2': { text: "प्यार कोई ऐसी चीज़ नहीं है जिसे आप ढूंढते हैं। प्यार वह चीज़ है जो आपको ढूंढती है।", author: "लोरेटा यंग" }, 'l3': { text: "प्यार एक ऐसा फूल है जो हर मौसम में खिल सकता है।", author: "अज्ञात" }, 'l4': { text: "हम सबसे ज़्यादा जीवित तब होते हैं जब हम प्यार में होते हैं।", author: "जॉन अपडाइक" }, 'l5': { text: "सच्चा प्यार कभी खत्म नहीं होता, वह बस यादों में बस जाता है।", author: "अज्ञात" }, 'l6': { text: "प्यार एक ही आत्मा से बना है जो दो शरीरों में निवास करती है।", author: "अरस्तू" }, 'l7': { text: "प्यार में गिरकर उठना नहीं, बल्कि गिरकर भी साथ चलना होता है।", author: "अज्ञात" }, 'l8': { text: "जीवन में पकड़ने के लिए सबसे अच्छी चीज एक दूसरे का साथ है।", author: " ऑड्रे हेपबर्न" }, 'l9': { text: "प्यार बिना शर्त देने का नाम है, वरना वो सिर्फ एक सौदा है।", author: "अज्ञात" }, 'l10': { text: "प्यार दुनिया को नहीं घुमाता। प्यार वह है जो यात्रा को सार्थक बनाता है।", author: "फ्रैंकलिन पी. जोन्स" },
                'm1': { text: "जब तक आप कोशिश नहीं करते, आप नहीं जानते कि आप क्या कर सकते हैं।", author: "अज्ञात" }, 'm2': { text: "विश्वास करो कि तुम कर सकते हो और तुम आधे रास्ते पर हो।", author: "थियोडोर रूजवेल्ट" }, 'm3': { text: "हार तभी मान लो जब दिल में जान न बची हो, वरना एक और कोशिश कभी नुकसान नहीं करती।", author: "अज्ञात" }, 'm4': { text: "आपकी सीमा—यह केवल आपकी कल्पना है।", author: "अज्ञात" }, 'm5': { text: "संघर्ष इंसान को पूर्ण बनाता है, सफलता नहीं।", author: "अज्ञात" }, 'm6': { text: "खुद को धकेलो, क्योंकि कोई और तुम्हारे लिए यह नहीं करेगा।", author: "अज्ञात" }, 'm7': { text: "जिंदगी में वही आगे बढ़ते हैं, जो मुश्किलों से लड़ते हैं।", author: "अज्ञात" }, 'm8': { text: "बड़े सपने देखो और असफल होने का साहस करो।", author: "नॉर्मन वॉन" }, 'm9': { text: "अगर रास्ता आसान होता, तो सभी मंजिल तक पहुँच जाते।", author: "अज्ञात" }, 'm10': { text: "आप किसी चीज़ के लिए जितनी मेहनत करते हैं, उसे हासिल करने पर आपको उतना ही अच्छा महसूस होगा।", author: "अज्ञात" },
                'mx1': { text: "जो डर गया, समझो वो मर गया।", author: "शोले (फिल्म संवाद)" }, 'mx2': { text: "यदि आप सूर्य की तरह चमकना चाहते हैं, तो पहले सूर्य की तरह जलें।", author: "ए पी जे अब्दुल कलाम" }, 'mx3': { text: "समय बदलता है, परिस्थितियाँ बदलती हैं, बस इरादे मजबूत होने चाहिए।", author: "अज्ञात" }, 'mx4': { text: "आप कभी भी दूसरा लक्ष्य निर्धारित करने या नया सपना देखने के लिए बहुत बूढ़े नहीं होते।", author: "सी.एस. लुईस" }, 'mx5': { text: "असंभव कुछ नहीं, बस हिम्मत चाहिए।", author: "अज्ञात" }, 'mx6': { text: "जो तुम प्यार करते हो वो करो, जो करते हो उससे प्यार करो।", author: "अज्ञात" }, 'mx7': { text: "जब तक जीना, तब तक सीखना।", author: "अज्ञात" }, 'mx8': { text: "महान कार्य करने का एकमात्र तरीका यह है कि आप जो करते हैं उससे प्यार करें।", author: "स्टीव जॉब्स" }, 'mx9': { text: "खुद को बदलो, किस्मत खुद बदल जाएगी।", author: "अज्ञात" }, 'mx10': { text: "सफलता उत्साह कम हुए बिना असफलता से असफलता तक चलना है।", author: "विंस्टन चर्चिल" }, 'mx11': { text: "जो सपने देखता है और हार नहीं मानता, वही इतिहास बनाता है।", author: "अज्ञात" }, 'mx12': { text: "आप उन 100% शॉट्स से चूक जाते हैं जिन्हें आप नहीं लेते हैं।", author: "वेन ग्रेट्ज़की" }, 'mx13': { text: "मुश्किलें तभी तक हैं, जब तक आप उन्हें मुश्किल मानते हैं।", author: "अज्ञात" }, 'mx14': { text: "दिनों को मत गिनो, दिनों को गिनने लायक बनाओ।", author: "मुहम्मद अली" }, 'mx15': { text: "जीतने की इच्छा से ज्यादा जरूरी, हारने के डर से लड़ने की हिम्मत है।", author: "अज्ञात" }, 'mx16': { text: "भविष्य इस पर निर्भर करता है कि आप आज क्या करते हैं।", author: "महात्मा गांधी" }, 'mx17': { text: "अगर आप अपने सपनों को पूरा करना चाहते हैं, तो पहले अपनी नींद पूरी करो।", author: "अज्ञात (मजेदार)" }, 'mx18': { text: "सफलता का प्रयास न करें, बल्कि मूल्यवान बनने का प्रयास करें।", author: "अल्बर्ट आइंस्टीन" }, 'mx19': { text: "जो दूसरों के लिए जीता है, वही सच में जीता है।", author: "अज्ञात" }, 'mx20': { text: "जीवन 10% वह है जो हमारे साथ होता है और 90% यह कि हम उस पर कैसे प्रतिक्रिया करते हैं।", author: "चार्ल्स आर. स्विंडोल" }
            }
        };

        // --- Utility & Core Functions ---
        function getTranslatedQuote(quoteId, lang) { /* ... (same) ... */ const defaultLang = 'en'; const translationsForLang = quoteContentTranslations[lang] || quoteContentTranslations[defaultLang]; const quoteData = (translationsForLang && translationsForLang[quoteId]) ? translationsForLang[quoteId] : (quoteContentTranslations[defaultLang] && quoteContentTranslations[defaultLang][quoteId]) ? quoteContentTranslations[defaultLang][quoteId] : { text: "Quote not found", author: "Unknown" }; return quoteData; }
        function showToast(messageKey, duration = 2000) { /* ... (same) ... */ const toast = document.getElementById('toast-container'); toast.textContent = (uiTranslations[selectedLanguage]?.[messageKey]) || messageKey; toast.classList.add('show'); setTimeout(() => { toast.classList.remove('show'); }, duration); }
        function applyTranslations() { /* ... (same, ensures updateDisplayedQuotesLanguage is called) ... */ const lang = selectedLanguage; document.querySelectorAll('[data-translate-key]').forEach(element => { const key = element.getAttribute('data-translate-key'); const translation = (uiTranslations[lang]?.[key]) || (uiTranslations['en']?.[key]); if (translation) { if (element.tagName === 'INPUT' && element.type === 'text' && element.placeholder) { element.placeholder = translation; } else if (element.dataset.placeholderKey && element.id === 'previewCanvasText') { const placeholderText = (uiTranslations[lang]?.[element.dataset.placeholderKey]) || (uiTranslations['en']?.[element.dataset.placeholderKey]); if (element.textContent === element.dataset.currentPlaceholderText || element.textContent.trim() === "") { element.textContent = placeholderText; element.dataset.currentPlaceholderText = placeholderText; } } else { element.innerHTML = translation; } } }); const langNameEl = document.querySelector(`#language-selection-screen .language-item[onclick*="'${lang}'"] span`); if(langNameEl){ document.getElementById('currentLanguageSetting').textContent = langNameEl.textContent.split(')')[0] + (lang !== 'en' && lang !== 'es' && lang !== 'hi' ? ')' : ''); } updateDisplayedQuotesLanguage(); if (currentScreenId === 'favorites-screen') renderFavorites(); if (document.getElementById('quote-detail-bottom-sheet').classList.contains('active')) { const currentBSQuoteId = document.getElementById('quote-detail-bottom-sheet').dataset.quoteId; if(currentBSQuoteId) { const bsq = getTranslatedQuote(currentBSQuoteId, selectedLanguage); document.getElementById('bsQuoteText').textContent = `"${bsq.text}"`; document.getElementById('bsQuoteAuthor').textContent = `- ${bsq.author}`; } } const homeScreenBg = document.querySelector('#home-screen .home-screen-gradient-bg'); if (homeScreenBg) { if (document.body.classList.contains('dark-theme')) { homeScreenBg.style.background = `linear-gradient(to bottom, var(--dark-primary-purple) 0%, var(--dark-primary-purple) 150px, var(--dark-bg) 150px, var(--dark-bg) 100%)`; } else { homeScreenBg.style.background = `linear-gradient(to bottom, var(--primary-purple) 0%, var(--primary-purple) 150px, var(--light-gray) 150px, var(--light-gray) 100%)`; } } }
        function updateDisplayedQuotesLanguage() { /* ... (Modified for daily QOTD logic) ... */
            // Daily QOTD
            const qotdData = getDailyQuote();
            const qotdCard = document.getElementById('qotdCard');
            if (qotdCard && qotdData) {
                qotdCard.dataset.quoteId = qotdData.id; // Update the card's quote ID
                const translatedQotd = getTranslatedQuote(qotdData.id, selectedLanguage);
                document.getElementById('qotdText').textContent = `"${translatedQotd.text}"`;
                document.getElementById('qotdAuthor').textContent = `- ${translatedQotd.author}`;
                const heartIcon = qotdCard.querySelector('.fa-heart');
                if (heartIcon) heartIcon.classList.toggle('favorited', favoriteQuoteIds.includes(qotdData.id));
            }

            // Trending Now (remains the same specific quote for demo)
            const trendingCard = document.getElementById('trendingNowCard');
            if (trendingCard) {
                const trendingId = trendingCard.dataset.quoteId; // 'q_beOfValue'
                const translatedTrending = getTranslatedQuote(trendingId, selectedLanguage);
                document.getElementById('trendingNowText').textContent = `"${translatedTrending.text}"`;
                document.getElementById('trendingNowAuthor').textContent = `- ${translatedTrending.author}`;
                const categoryKey = allQuotes[trendingId] ? ('category' + allQuotes[trendingId].category) : 'categoryMotivation';
                const categoryElement = document.getElementById('trendingNowCategory');
                categoryElement.textContent = (uiTranslations[selectedLanguage]?.[categoryKey]) || (uiTranslations['en']?.[categoryKey]) || allQuotes[trendingId]?.category || "Motivation";
                const heartIconTrending = trendingCard.querySelector('.fa-heart');
                if(heartIconTrending) heartIconTrending.classList.toggle('favorited', favoriteQuoteIds.includes(trendingId));
            }
            if (currentScreenId === 'explore-screen') {
                const activeFilterBtn = document.querySelector('#explore-screen .filter-btn.active');
                if (activeFilterBtn) {
                    const onclickAttr = activeFilterBtn.getAttribute('onclick');
                    const filterTypeMatch = onclickAttr.match(/applyExploreFilter\(this, '([^']*)'/);
                    const valueMatch = onclickAttr.match(/, '([^']*)'\)/);
                    const filterType = filterTypeMatch ? filterTypeMatch[1] : 'all';
                    const filterValue = valueMatch ? valueMatch[1] : null;
                    populateExploreGrid(filterType === 'category' ? filterValue : (filterType === 'all' ? null : filterType));
                } else {
                     populateExploreGrid();
                }
            }
        }
        function createBottomNav() { /* ... (same) ... */ if (document.getElementById('appBottomNav')) return; const template = document.getElementById('bottom-nav-template').cloneNode(true); template.id = 'appBottomNav'; template.className = 'bottom-nav'; template.style.display = 'flex'; template.querySelectorAll('.nav-item').forEach(item => { item.addEventListener('click', () => { const screenId = item.getAttribute('data-screen'); showScreen(screenId, true); }); }); document.body.appendChild(template); bottomNavElement = template; applyTranslations(); }
        function updateBottomNavActiveState(screenId) { /* ... (same) ... */ if (bottomNavElement) { bottomNavElement.querySelectorAll('.nav-item').forEach(item => { item.classList.toggle('active', item.getAttribute('data-screen') === screenId); }); } }
        function showScreen(screenId, hasNav = false) { /* ... (same) ... */ if (currentScreenId) { const currentScreenElement = document.getElementById(currentScreenId); if (currentScreenElement) currentScreenElement.classList.remove('active'); } const newScreenElement = document.getElementById(screenId); if (newScreenElement) { newScreenElement.classList.add('active'); currentScreenId = screenId; const contentScroller = newScreenElement.querySelector('.screen-content') || newScreenElement; contentScroller.scrollTop = 0; if (screenId === 'explore-screen') populateExploreGrid(); if (screenId === 'favorites-screen') renderFavorites(); } else { console.error("Screen not found:", screenId); return; } if (hasNav && screensWithNav.includes(screenId)) { if (!bottomNavElement || !document.getElementById('appBottomNav')) { createBottomNav(); } bottomNavElement.style.display = 'flex'; updateBottomNavActiveState(screenId); } else if (bottomNavElement) { bottomNavElement.style.display = 'none'; } applyTranslations(); }
        function selectLanguage(element, langCode) { /* ... (same) ... */ document.querySelectorAll('#language-selection-screen .language-item').forEach(item => { item.classList.remove('selected'); }); element.classList.add('selected'); selectedLanguage = langCode; applyTranslations(); }
        const themeToggleSwitch = document.getElementById('themeToggleSwitch'); themeToggleSwitch.addEventListener('change', function() { /* ... (same) ... */ document.body.classList.toggle('dark-theme', this.checked); applyTranslations(); });
        function copyToClipboard(text) { /* ... (same) ... */ navigator.clipboard.writeText(text).then(() => { showToast('alertCopied'); }).catch(err => { console.error('Failed to copy: ', err); }); }
        function copyQuoteContent(quoteId) { /* ... (same) ... */ const quote = getTranslatedQuote(quoteId, selectedLanguage); copyToClipboard(`"${quote.text}" - ${quote.author}`); }
        function toggleFavorite(quoteId, heartIconElement) { /* ... (Modified to use localStorage) ... */
            const index = favoriteQuoteIds.indexOf(quoteId);
            if (index > -1) {
                favoriteQuoteIds.splice(index, 1);
                if (heartIconElement) heartIconElement.classList.remove('favorited');
                showToast('alertUnfavorited');
            } else {
                favoriteQuoteIds.push(quoteId);
                if (heartIconElement) heartIconElement.classList.add('favorited');
                showToast('alertFavorited');
            }
            localStorage.setItem('favoriteQuoteIds', JSON.stringify(favoriteQuoteIds)); // Save to localStorage
            // Update all relevant heart icons
            document.querySelectorAll(`.fa-heart`).forEach(icon => {
                const card = icon.closest('.card, .quote-grid-item'); // Find parent card or grid item
                if (card && card.dataset.quoteId === quoteId) {
                    icon.classList.toggle('favorited', favoriteQuoteIds.includes(quoteId));
                }
            });
            if (currentScreenId === 'favorites-screen') renderFavorites();
        }
        function exploreByCategory(categoryName) { /* ... (same) ... */ showScreen('explore-screen', true); const filterButton = Array.from(document.querySelectorAll('#explore-screen .filter-btn')).find( btn => { const btnTextKey = btn.getAttribute('data-translate-key'); const translatedCatName = (uiTranslations[selectedLanguage]?.[btnTextKey] || btnTextKey).toLowerCase(); return translatedCatName === categoryName.toLowerCase(); }); if (filterButton) { const onclickAttr = filterButton.getAttribute('onclick'); const filterTypeMatch = onclickAttr.match(/applyExploreFilter\(this, '([^']*)'/); const valueMatch = onclickAttr.match(/, '([^']*)'\)/); const filterType = filterTypeMatch ? filterTypeMatch[1] : 'category'; const filterValue = valueMatch ? valueMatch[1] : categoryName; applyExploreFilter(filterButton, filterType, filterValue); } else { populateExploreGrid(categoryName, 'category'); showToast(uiTranslations[selectedLanguage].alertExploreFilter + categoryName); const rawMatchButton = Array.from(document.querySelectorAll('#explore-screen .filter-btn')).find( btn => btn.getAttribute('onclick').includes(`'${categoryName}'`) ); if(rawMatchButton){ document.querySelectorAll('#explore-screen .filter-btn').forEach(b => b.classList.remove('active')); rawMatchButton.classList.add('active'); } } }
        function populateExploreGrid(filterValue = null, filterType = 'category') { /* ... (same) ... */ const grid = document.getElementById('exploreQuoteGrid'); grid.innerHTML = ''; let quotesToDisplayIds = Object.keys(allQuotes); if (filterValue) { if (filterType === 'category') { quotesToDisplayIds = quotesToDisplayIds.filter(id => allQuotes[id].category.toLowerCase() === filterValue.toLowerCase()); } } quotesToDisplayIds.forEach(quoteId => { const quoteData = getTranslatedQuote(quoteId, selectedLanguage); const item = document.createElement('div'); item.className = 'quote-grid-item card'; item.dataset.quoteId = quoteId; item.innerHTML = `<p>"${quoteData.text}"</p><span class="author">- ${quoteData.author}</span><div class="quote-actions" style="margin-top: 5px; justify-content: flex-start; gap: 10px;"><i class="fas fa-heart ${favoriteQuoteIds.includes(quoteId) ? 'favorited' : ''}" onclick="event.stopPropagation(); toggleFavorite('${quoteId}', this)"></i><i class="fas fa-copy" onclick="event.stopPropagation(); copyQuoteContent('${quoteId}')"></i></div>`; item.onclick = () => openQuoteDetail(quoteId); grid.appendChild(item); }); }
        function applyExploreFilter(btnElement, filterType, value = null) { /* ... (same) ... */ document.querySelectorAll('#explore-screen .filter-btn').forEach(btn => btn.classList.remove('active')); btnElement.classList.add('active'); const filterText = value || (filterType === 'all' ? (uiTranslations[selectedLanguage].filterAll || 'All') : filterType); showToast(uiTranslations[selectedLanguage].alertExploreFilter + filterText); populateExploreGrid(filterType === 'all' ? null : value, filterType); }
        // --- Create Status Screen (saveStatusAsImage and related functions are same) ---
        const previewCanvasElement = document.getElementById('previewCanvas'); const previewCanvasText = document.getElementById('previewCanvasText'); const subToolsContainer = document.getElementById('subToolsContainer'); let activeSubTool = null;
        previewCanvasText.addEventListener('focus', () => { const placeholderKey = previewCanvasText.dataset.placeholderKey; const currentPlaceholder = (uiTranslations[selectedLanguage]?.[placeholderKey]) || (uiTranslations['en']?.[placeholderKey]) || ""; if (previewCanvasText.textContent === currentPlaceholder) { previewCanvasText.textContent = ''; } });
        previewCanvasText.addEventListener('blur', () => { const placeholderKey = previewCanvasText.dataset.placeholderKey; const currentPlaceholder = (uiTranslations[selectedLanguage]?.[placeholderKey]) || (uiTranslations['en']?.[placeholderKey]) || ""; if (previewCanvasText.textContent.trim() === '') { previewCanvasText.textContent = currentPlaceholder; } });
        function toggleSubTool(toolName) { const currentActiveToolItem = document.querySelector('#create-status-screen .tool-item.active'); if (currentActiveToolItem) currentActiveToolItem.classList.remove('active'); const toolItem = Array.from(document.querySelectorAll('#create-status-screen .tool-item')).find(el => el.onclick.toString().includes(`'${toolName}'`)); if (toolItem) toolItem.classList.add('active'); if (activeSubTool === toolName) { subToolsContainer.innerHTML = ''; activeSubTool = null; if (toolItem) toolItem.classList.remove('active'); return; } activeSubTool = toolName; subToolsContainer.innerHTML = ''; const panel = document.createElement('div'); panel.className = 'sub-tool-panel active'; switch (toolName) { case 'background': panel.innerHTML = `<input type="color" id="bgColorPicker" title="Background Color"><button onclick="setCanvasBgImage('https://picsum.photos/seed/Quotezy1/400/600')">Img 1</button><button onclick="setCanvasBgImage('https://picsum.photos/seed/Quotezy2/400/600')">Img 2</button><button onclick="previewCanvasElement.style.backgroundImage = 'none'; previewCanvasElement.style.backgroundColor = '#8BC6EC';">Reset</button>`; panel.querySelector('#bgColorPicker').oninput = (e) => previewCanvasElement.style.backgroundColor = e.target.value; break; case 'text': panel.innerHTML = `Text Editing (Not fully implemented)`; previewCanvasText.focus(); break; case 'font': const fonts = ['Arial', 'Verdana', 'Georgia', 'Courier New', 'Brush Script MT', 'Poppins']; fonts.forEach(f => { const btn = document.createElement('button'); btn.className = 'font-option'; btn.textContent = f; btn.style.fontFamily = f; btn.onclick = () => previewCanvasText.style.fontFamily = f; panel.appendChild(btn); }); break; case 'emoji': const emojis = ['😀', '😍', '👍', '🎉', '💡', '❤️']; emojis.forEach(e => { const span = document.createElement('span'); span.className = 'emoji-option'; span.textContent = e; span.onclick = () => { const phKey = previewCanvasText.dataset.placeholderKey; const phText = (uiTranslations[selectedLanguage]?.[phKey])||(uiTranslations['en']?.[phKey]); if (previewCanvasText.textContent === phText) previewCanvasText.textContent = ''; previewCanvasText.textContent += e; }; panel.appendChild(span); }); break; case 'color': panel.innerHTML = `<input type="color" id="textColorPicker" title="Text Color" value="${previewCanvasText.style.color || '#FFFFFF'}">`; panel.querySelector('#textColorPicker').oninput = (e) => previewCanvasText.style.color = e.target.value; break; } subToolsContainer.appendChild(panel); }
        function setCanvasBgImage(url) { previewCanvasElement.style.backgroundImage = `url(${url})`; previewCanvasElement.style.backgroundSize = 'cover'; previewCanvasElement.style.backgroundPosition = 'center'; }
        function saveStatusAsImage() { /* ... (same as previous, uses html2canvas) ... */ const text = previewCanvasText.textContent; const placeholderKey = previewCanvasText.dataset.placeholderKey; const currentPlaceholder = (uiTranslations[selectedLanguage]?.[placeholderKey]) || (uiTranslations['en']?.[placeholderKey]) || ""; if (text && text.trim() !== currentPlaceholder.trim() && text.trim() !== "") { html2canvas(previewCanvasElement, { allowTaint: true, useCORS: true, backgroundColor: getComputedStyle(previewCanvasElement).backgroundColor }).then(canvas => { const imageURL = canvas.toDataURL('image/png'); const downloadLink = document.createElement('a'); downloadLink.href = imageURL; downloadLink.download = `Quotezy_${Date.now()}.png`; document.body.appendChild(downloadLink); downloadLink.click(); document.body.removeChild(downloadLink); showToast('alertStatusSaved'); previewCanvasText.textContent = currentPlaceholder; previewCanvasText.dataset.currentPlaceholderText = currentPlaceholder; previewCanvasText.style.fontFamily = 'Poppins'; previewCanvasText.style.color = 'white'; previewCanvasElement.style.backgroundImage = 'none'; previewCanvasElement.style.backgroundColor = ''; if (activeSubTool) toggleSubTool(activeSubTool); showScreen('home-screen', true); }).catch(err => { console.error("Error generating image:", err); showToast("Error generating image. Try a solid background."); }); } else { showToast('alertStatusEmpty'); } }

        // --- Favorites Screen ---
        function renderFavorites() { /* ... (same) ... */ const container = document.getElementById('favoritesListContainer'); const noFavsMsg = document.getElementById('no-favorites-message'); container.innerHTML = ''; container.appendChild(noFavsMsg); if (favoriteQuoteIds.length === 0) { noFavsMsg.style.display = 'block'; return; } noFavsMsg.style.display = 'none'; favoriteQuoteIds.forEach(quoteId => { const quoteData = getTranslatedQuote(quoteId, selectedLanguage); const categoryKey = (allQuotes[quoteId] && allQuotes[quoteId].category) ? 'category' + allQuotes[quoteId].category : 'categoryGeneral'; const categoryText = (uiTranslations[selectedLanguage]?.[categoryKey]) || (uiTranslations['en']?.[categoryKey]) || (allQuotes[quoteId]?.category) || 'General'; const item = document.createElement('div'); item.className = 'favorite-item card'; item.dataset.quoteId = quoteId; item.innerHTML = `<span class="category-tag">${categoryText}</span><p class="quote-text">"${quoteData.text}"</p><p class="quote-author">- ${quoteData.author}</p><div class="actions"><i class="fas fa-heart favorited" onclick="toggleFavorite('${quoteId}', this)"></i><i class="fas fa-copy" onclick="copyQuoteContent('${quoteId}')"></i><i class="fas fa-trash-alt" onclick="deleteFavoritePermanently('${quoteId}')"></i></div>`; container.appendChild(item); }); }
        function deleteFavoritePermanently(quoteId) { /* ... (same, uses localStorage) ... */ favoriteQuoteIds = favoriteQuoteIds.filter(id => id !== quoteId); localStorage.setItem('favoriteQuoteIds', JSON.stringify(favoriteQuoteIds)); showToast('alertUnfavorited'); renderFavorites(); document.querySelectorAll(`#home-screen .quote-card[data-quote-id="${quoteId}"] .fa-heart, #explore-screen .quote-grid-item[data-quote-id="${quoteId}"] .fa-heart`).forEach(icon => { icon.classList.remove('favorited'); }); }

        // --- Bottom Sheet ---
        // openQuoteDetail, closeQuoteDetail, copyFromBottomSheet, favoriteFromBottomSheet, shareFromBottomSheet, createImageFromBottomSheet (same as previous)
        const bottomSheet = document.getElementById('quote-detail-bottom-sheet'); const bottomSheetOverlay = document.getElementById('bottomSheetOverlay'); const bsQuoteText = document.getElementById('bsQuoteText'); const bsQuoteAuthor = document.getElementById('bsQuoteAuthor'); let currentBsQuoteId = null;
        function openQuoteDetail(quoteId) { currentBsQuoteId = quoteId; bottomSheet.dataset.quoteId = quoteId; const quoteData = getTranslatedQuote(quoteId, selectedLanguage); bsQuoteText.textContent = `"${quoteData.text}"`; bsQuoteAuthor.textContent = `- ${quoteData.author}`; bottomSheet.classList.add('active'); bottomSheetOverlay.classList.add('active'); document.body.style.overflow = 'hidden'; }
        function closeQuoteDetail() { bottomSheet.classList.remove('active'); bottomSheetOverlay.classList.remove('active'); document.body.style.overflow = 'auto'; currentBsQuoteId = null; bottomSheet.removeAttribute('data-quote-id'); }
        function copyFromBottomSheet() { if(currentBsQuoteId) copyQuoteContent(currentBsQuoteId); }
        function favoriteFromBottomSheet() { if(currentBsQuoteId) toggleFavorite(currentBsQuoteId, null); }
        function shareFromBottomSheet() { if(currentBsQuoteId) { const q = getTranslatedQuote(currentBsQuoteId, selectedLanguage); const shareData = { title: 'Quotezy Quote', text: `"${q.text}" - ${q.author}\nShared via Quotezy`}; if (navigator.share) { navigator.share(shareData).catch(err => console.log('Error sharing:', err)); } else { showToast('alertNotImplemented'); } } }
        function createImageFromBottomSheet() { showToast('alertNotImplemented'); }

        // --- Onboarding Logic ---
        function nextOnboardingSlide(current) {
            showScreen(`onboarding-screen-${current + 1}`);
            currentOnboardingSlide = current + 1;
        }
        function finishOnboarding() {
            localStorage.setItem('onboardingCompleted', 'true');
            // If language selection is part of onboarding, show it. Otherwise, home.
            showScreen('language-selection-screen'); // Or directly 'home-screen' if no lang select after onboarding
        }
        function completeLanguageSelection() {
            // This function is called after language is selected if onboarding was shown
            // Or if onboarding was skipped and lang selection is the first step.
             const onboardingCompleted = localStorage.getItem('onboardingCompleted') === 'true';
            if (!onboardingCompleted) { // If coming from onboarding flow, mark it complete
                 localStorage.setItem('onboardingCompleted', 'true');
            }
            showScreen('home-screen', true);
        }

        // --- Daily Quote Logic ---
        function getDailyQuote() {
            const today = new Date().toISOString().slice(0, 10); // YYYY-MM-DD
            let dailyQuoteData = JSON.parse(localStorage.getItem('dailyQuote')) || {};

            if (dailyQuoteData.date !== today || !dailyQuoteData.id) {
                // New day or no quote stored, pick a new one
                const randomIndex = Math.floor(Math.random() * qotdPool.length);
                const newQuoteId = qotdPool[randomIndex];
                dailyQuoteData = { id: newQuoteId, date: today };
                localStorage.setItem('dailyQuote', JSON.stringify(dailyQuoteData));
            }
            return dailyQuoteData; // Returns {id: "...", date: "..."}
        }


        // --- Initial Load ---
        document.addEventListener('DOMContentLoaded', () => {
            // Load favorites from localStorage
            const storedFavorites = localStorage.getItem('favoriteQuoteIds');
            if (storedFavorites) {
                favoriteQuoteIds = JSON.parse(storedFavorites);
            }

            // Select default language (can be stored in localStorage too if needed)
            selectLanguage(document.querySelector('#language-selection-screen .language-item'), 'en'); // Default to English

            const initialPlaceholderKey = previewCanvasText.dataset.placeholderKey;
            const initialPlaceholderText = (uiTranslations['en']?.[initialPlaceholderKey]) || "Type your status...";
            previewCanvasText.textContent = initialPlaceholderText;
            previewCanvasText.dataset.currentPlaceholderText = initialPlaceholderText;

            // Initial quote display before screen logic
            updateDisplayedQuotesLanguage();

            // Onboarding check
            const onboardingCompleted = localStorage.getItem('onboardingCompleted') === 'true';

            if (!onboardingCompleted) {
                showScreen('splash-screen');
                setTimeout(() => {
                    showScreen('onboarding-screen-1');
                }, 1500); // Shorter splash for onboarding
            } else {
                // If onboarding is done, check if language was ever selected.
                // For simplicity, we'll assume if onboarding is done, language was selected.
                // A more robust app might store `languageSelected` flag too.
                showScreen('splash-screen');
                 setTimeout(() => {
                    showScreen('home-screen', true);
                }, 1500);
            }
        });

    </script>
</body>
</html>
