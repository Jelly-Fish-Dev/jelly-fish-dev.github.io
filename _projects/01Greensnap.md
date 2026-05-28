---
title: Greensnap
awards: Hackvision 2021 First Place
description:  Effective disposal of recyclable waste is elusive no more with GreenSnap! Simply scan your waste to find the best locations in your community to dispose of it in the most sustainable way.
hackathon: https://devpost.com/software/greensnap-j81rc3
date: 20-11-2021
layout: project
Author: Isaac Hawkins
---
<iframe width="640" height="360" src="https://www.youtube.com/embed/FfJe2Lm-nLQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Inspiration

Effective recycling and reuse of waste materials within our communities is almost non-existent. With many individuals being unaware of the correct disposal practices, incorrect usage of colored bins and councils allowing it to happen by simply redirecting recycling bins to hard rubbish tips. In the depths of both a climate crisis and a growing material shortage, it is more important now then ever to ensure our waste ends up in the location that is best for it.

Although there is currently information informing the public of the waste disposal practices for their local area, it is highly fragmented, with information of varying quality buried deep within complex and dated council websites. If people have to look too hard they will give up, especially when the alternate option is throwing the item in to the red bin half a meter away.

### What it does

Our app utilises the device's camera to take a picture of an item of waste. The image is sent to Google Vision which employs machine learning to detect items and materials in the image. These are then compared to an ever growing list of waste and resource centers to match up the item with centers that accept those materials.

The waste doesn't have to end up at resource centers though, with the ability for community members to request certain types of materials that can be used for both community and DIY projects. This ensures that the waste can be used within the community were possible, which is beneficial for both the planet and the members of the community.

### How we built it

We built our app with a number of the United Nation's Sustainable Development Goals in mind, including Sustainable Cities and Communities (#11), Responsible Consumption and Production (#12), Climate Action (#13), Life Below Water (#14) and Life on Land (#15).

Our application was first designed in Figma to ensure all of the developers were on the same page as the designers so that our app is cohesive and fluent from it's inception.

The frontend is created with React whilst the backend is built upon Firebase, allowing our app to be highly flexible and scalable due to it's serverless nature. Firebase handles user authentication, data storage through Firestore and acts as the entry point to the Google Vision API through Cloud Functions. The project is hosted through Firebase Hosting, to ensure that we take the most advantage of the platform. These technologies each allowed us to iterate quickly and pack our app full of many features, as well as providing us plenty of room to grow moving forward.

The item categorisation is undertaken by Google Vision, which uses machine learning to find labels within images. These images are captured on the frontend via native JavaScript APIs, and sent to the Google Vision API via a Cloud Function. The resulting tags are sent back to the client where they can be used to continue the experience.
### Challenges we ran into

A major challenge we faced was the JavaScript APIs required to capture images from a device's camera. The support across different browsers (particularly non-chromium mobile browsers) is generally quite fragmented and poor, resulting in a difficult time for the developers. In order to achieve better support, alternate image upload methods can be used, such as a simple file upload which will still allow the user to use their camera, but it will be handled by the operating system. Although this is a viable solution, we ultimately decided to stick with capturing the image within our app, to ensure the user has a very cohesive and smooth experience.

Another challenge was finding a package that provided a React component for Google Maps. The official Google Maps React wrapper had very few downloads and lots of problems that made it unusable. For this reason we had to switch to a third party module, although it turned out to be for the better, as it had many more weekly downloads and support online.

### Accomplishments that we're proud of

As a team, we are very proud of the scope we were able to cover within the 24 hour deadline. Our submission is both visually refined and functional, including complex features such as machine learning and image capture.

We are quite proud of our utilisation of Google's various products. Although across the team we have had a bit of experience, pulling together all of the combined knowledge and experimentation to create the app is something we are very happy with.

Finally, we are proud of the pitch video. We feel like it is simultaneously highly informative for the audience, whilst capturing the tone of a more tightly refined product with a much larger time and money budget.
### What we learned

We learned a lot about interfacing with a number of Google's products, particularly those found in Firebase and the Google Vision API. They proved to be imperative to iterating quickly and implementing the feature set that we desired.

Google Vision proved to be extremely powerful, highlighting the potential for machine learning within similar applications. Google Vision itself contains many more features than what we used in this app, indicating that there is still many ways to grow and improve with time.

In a similar manner, Firebase contains many more features that we did not get a chance to implement during this hackathon. For instance, Firestore allows for real time updates which we could utilise to create an application that shares partial state across different devices. This could be used for a live counter for a challenge, where the value can be updated as people drop off their waste in real time.

It was also a learning process understanding how to capture images with JavaScript. It required a lot of digging through documentation, due to the relatively obscure and under-utilised nature of the APIs, so there were very minimal examples online.
### What's next for GreenSnap

There are so many ways we can grow the app from here.

The app can be greatly improved with the addition of more data, particularly resource centers and the types of materials they accept. This will show more items on the map, and give much better results when an item has been scanned.

Another improvement would be to build out the community aspect more, allowing for users to create posts, request materials and create challenges. This will be quite important, as the community is a primary focus for the app, so they need to feel like they are helping and interacting with those around them.

Finally, converting the app to a progressive web app will provide the user with a near native experience, with the app appearing on their home screen, working offline (excluding the categorisation of images) and also being able to receive notifications. As with the camera, support across browsers (particularly Safari on iOS) is very spotty and may introduce some compatibility issues, but it would definitely be worth a try.
