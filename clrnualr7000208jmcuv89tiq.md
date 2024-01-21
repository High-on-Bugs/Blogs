---
title: "NewsCom: Unleashing Community Voices"
datePublished: Sun Jan 21 2024 18:36:14 GMT+0000 (Coordinated Universal Time)
cuid: clrnualr7000208jmcuv89tiq
slug: newscom
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705862116141/faf9afa2-435a-4c8b-b10a-de9f09730fe5.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1705862148627/d7d6239b-30c6-4dc3-b6a3-3877b16db926.jpeg
tags: github, community, reactjs

---

What started as a simple project to learn GitHub Actions became a potentially powerful conduit for collaboration. NewsCom envisages diverse voices to converge to share insights, experiences, and stories. In this blog, we embark on a journey through a unique project's inception, development, and intricacies. This community-driven newsletter thrives on the collective wisdom of its contributors.

## **The Purpose and Goals**

At the heart of this initiative lies a simple yet profound purpose: to cultivate a space where tech gets written by and for techies at minimal setup. This community newsletter is not just a platform for disseminating information; it is a testament to the power of collaborative storytelling, where the richness of shared experiences transcends boundaries. It aims to create a space with a detached content contribution system all the while maintaining a certain degree of ownership.

## **GitHub Authentication: A Pillar of Security and Engagement**

To maintain content ownership and maintain a secure environment, we've implemented user authentication through GitHub accounts. This streamlines the contribution process and adds an extra layer of trust and accountability to the community.

By leveraging GitHub's robust authentication system, we not only enhance the security of our platform but also seamlessly integrate with a vast network of developers and enthusiasts. This unique approach not only simplifies the registration process (more like signing, in our case) but also taps into the pre-existing GitHub community, creating a familiar and welcoming environment for users.

## **Creating and Submitting Articles on the Webpage**

With the foundation of GitHub authentication laid out in the previous chapter, we now turn our attention to the heart of our community-driven newsletter project – the process of creating and submitting articles. Our dedicated webpage serves as a simple Markdown editor where contributors, armed with their GitHub identities, can weave their narratives and share their insights. Any GitHub User needs 5 steps to potentially contribute their first article:

* Go to [https://newscom.sbk2k1.tech/](https://newscom.sbk2k1.tech/)
    
* Sign in with GitHub by clicking on "Write a Blog Yourself".
    
* Authenticate GitHub App.
    
* Click on "Write a Blog Yourself".
    
* Write and Submit!
    

As contributors craft their articles, the integration with GitHub ensures that each iteration is tracked and worked with seamlessly. Once an article takes shape and the contributor is satisfied, our platform facilitates the submission process through a straightforward interface. This can also foster a better understanding of Git and GitHub amongst developers.

## **Pull Requests and Collaborative Editing**

In the collaborative ecosystem of our community newsletter, the editorial process takes center stage as repository collaborators assume the role of editors. GitHub pull requests (PRs) become the conduit through which individual contributions undergo scrutiny, refinement, and ultimately, integration into the collective narrative.  
  
**Collaborators as Editors**

Within our GitHub repository, a select group of individuals – our repository collaborators – take on the pivotal role of editors. Endowed with the responsibility of reviewing and curating content, these collaborators evaluate each pull request based on the project's editorial guidelines. Their expertise ensures that the newsletter maintains a high standard of quality, coherence, and relevance.

## Automation with GitHub Actions

GitHub Actions, a powerful workflow automation tool, becomes the silent orchestrator behind the scenes, ensuring that our community newsletter project runs seamlessly. This chapter explores the role of GitHub Actions in automating critical processes, from triggering events based on article collection milestones to compiling and distributing the newsletter to our eager subscribers.

#### **Triggering Actions: From Collection to Compilation**

One of the primary functions of GitHub Actions in our project is the automatic triggering of workflows based on predefined conditions. As articles accumulate in the main branch (collecting), a GitHub Action is set to activate when a certain number is reached. This marks the commencement of the compilation process, ensuring that the newsletter evolves organically.

#### **Email Notifications: Connecting with Subscribers**

With the compiled newsletter in hand, GitHub Actions takes the next step by automating the distribution process. Subscribers, eagerly awaiting the latest edition, receive automated email notifications. This ensures timely and consistent delivery, enhancing the overall user experience and engagement.

#### **Cleanup and Cloudinary Backup**

In the spirit of meticulous housekeeping, GitHub Actions goes a step further by cleaning up the main branch post-compilation. This ensures a fresh slate for the next collection cycle. Simultaneously, a backup process sends the compiled files to Cloudinary, providing a secure archive for previous issues. This strategic backup strategy adds an extra layer of protection against data loss.

***Note: Currently a user can write only 1 article per day.***

## Future Decisions

Currently, the project has quite a few shortcomings. The front end and UI are **not the best**. The IDE and the overall feel are not very user-friendly. Moreover, there is no subscribe and publish feature, since they will need cloud-hosted services (at least the database). I'll push these features when there are ***at least 50 article submissions***.

## **Conclusion**

The project is centered around minimal setup and simple workflow. I'll try to keep improving on that. Careful curation of articles is something I think I'd have to focus a lot on in terms of upscaling.

## Technologies used

* **GitHub Actions:** Used for automating workflows, such as triggering events based on article collection milestones, compiling Markdown articles, and distributing the newsletter.
    
* **Node.js:** Backend proxy, handling publish, etc etc
    
* **React.js:** The website
    
* **Octokit:** A JavaScript toolkit for the GitHub API. It facilitates communication with the GitHub API, allowing seamless integration and interaction with GitHub features.
    
* **GitHub API and OAuth:** GitHub API is likely used for accessing and manipulating GitHub data, while OAuth is employed for secure and standardized user authentication using GitHub accounts.
    
* **GitHub Version Control:** Inherent to the GitHub platform, version control is fundamental for tracking changes, managing branches, and ensuring the integrity of the project's codebase.
    

---

* Website: [https://newscom.sbk2k1.tech/](https://newscom.sbk2k1.tech/)
    
* GitHub Repo: [https://github.com/High-on-Bugs/HoB-Community-Newsletter](https://github.com/High-on-Bugs/HoB-Community-Newsletter)
    

If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!