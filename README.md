# JS Mastery YouTube-Clone Project

![Landing Page Screenshot](./screenshot.png?raw=true "Landing Page")

## Overview

This is a project to create a clone of the YouTube web app by leveraging the YouTube V3 API endpoints provided by the RapidAPI platform. The project was built from this [youtube tutorial](https://www.youtube.com/watch?v=FHTbsZEJspU).

## Prerequisites

- Installing Node JS & NPM in your local machine. See how [here](https://www.youtube.com/watch?v=X-FPCwZFU_8)
- How to use React JS to create frontend web applications. See how [here](https://reactjs.org/tutorial/tutorial.html)

## Links

- Solution URL: [Solution on GitHub](https://github.com/Wandonium/youtube_clone)
- Live Site URL: [Live Site on Netlify](https://dazzling-starburst-b0078e.netlify.app/)
- Rapid API: [YouTube V3 API](https://rapidapi.com/ytdlfree/api/youtube-v31)

## Run Code locally

To run the project locally, please follow the steps given below.

- Clone this Repository

  ```bash
  git clone https://github.com/Wandonium/youtube_clone
  ```

- Go to Project directory

  ```bash
  cd youtube_clone
  ```

- Start the project using webpack

  ```bash
  npm start
  ```
## My process

### Built with

- React JS
- Material UI
- Rapid API
- Axios
- React-Router-Dom
- Flexbox
- Mobile-first workflow


### What I learned

How to setup axios with a base url for the API and export a function to be reused with different API endpoints in different React components

```jsx
import axios from 'axios';

const BASE_URL = 'https://youtube-v31.p.rapidapi.com';

const options = {
    url: BASE_URL,
    withCredentials: false,
    params: {
      maxResults: '50'
    },
    headers: {
      'X-RapidAPI-Key': process.env.REACT_APP_RAPID_API_KEY,
      'X-RapidAPI-Host': 'youtube-v31.p.rapidapi.com'
    }
};

export const fetchFromAPI = async(url) => {
     const { data } = await axios.get(`${BASE_URL}/${url}`, options);
     return data;
}
```

How to use the Material UI sx prop in various MUI components to target different device screen sizes just like how we do it with media queries in CSS.

```jsx
<Card sx={{ 
    width: { xs: '90vw', sm: '358px', md: '320px' }, 
    boxShadow: 'none', 
    borderRadius: 0 
}}>
    ...
</Card>
```
How to use the BrowserRouter component of react-router-dom package to setup page routing in the root of my React app.

```jsx
<BrowserRouter>
    <Box sx={{ backgroundColor: '#000'}}>
        <Navbar />
        <Routes>
            <Route path="/" exact element={<Feed />} />
            <Route path="/video/:id" element={<VideoDetail />} />
            <Route path="/channel/:id" element={<ChannelDetail />} />
            <Route path="/search/:searchTerm" element={<SearchFeed />} />
        </Routes>
    </Box>
</BrowserRouter>
```

## Author

- Website - [Hillary Wando](http://hillarywando.com/)
- Twitter - [@hillarywando](https://www.twitter.com/hillarywando)

<!-- It is mandatory to add this.-->

Any comments, suggestions or corrections are welcome. Contribution are welcome as This repository is licensed under [MIT](https://opensource.org/licenses/MIT) License.