<template>
    <div class="bg-black h-screen px-6 py-12">
        <h2 class="text-white font-museo text-5xl opacity-0" ref="title" style="transform: translateY(30px);">Click any picture to Enter Qujuan Miller's Portfolio</h2>
        <div class="flex space-x-4">
            <div ref="projects" v-for="project in projects" class="w-full opacity-0" style="transform: translateX(30px);">
               <a href="https://qujuanmiller-portfolio.netlify.app/">
                <img :src="project.image.url" alt="4"
                style="height: 80vh;" class="object-cover">
            
                <p class="text-white font-tomorrow text-sm">{{ project.title }}</p>
               </a>
            </div>
           
        </div>
    </div>
</template>

<script>
import gsap from 'gsap'
import androidImg from '~/assets/4.jpg'
import reactImg from '~/assets/3.jpg'
import gameDevImg from '~/assets/5.jpg'
import threeJsImg from '~/assets/2.jpg'
import appleImg from '~/assets/1.jpg'
export default {
    data() {
        return {
            projects: [
                {
                    image: {
                        url: androidImg
                    },
                    title: 'Android Development',
                },
                {
                    image: {
                        url: reactImg
                    },
                    title: 'Web Development'
                },
                {
                    image: {
                        url: gameDevImg
                    },
                    title: 'Game Development'
                },
                {
                    image: {
                        url: threeJsImg
                    },
                    title: 'Threejs Development'
                },
                {
                    image: {
                        url: appleImg
                    },
                    title: 'iOS Development'
                },
            ]
        }
    },
    mounted() {
        gsap.to(this.$refs.title, {
            opacity:1,
            duration: 1,
            y: 0,
            ease: 'expo'
        })

        gsap.to(this.$refs.projects, {
            opacity: 1,
            duration: 1,
            stagger: 0.2,
            x: 0,
            ease: 'expo',
            delay: 0.3
        })
    }
}
</script>