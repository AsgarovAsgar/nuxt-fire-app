<template>
    <div class="flex justify-between">
        <div class="flex flex-col space-y-4">
            <h1 class="text-8xl font-extrabold">Find your Fire Extinguisher</h1>
            <p class="text-xl text-gray-500">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Iste iusto illum quidem asperiores, cum nisi aperiam eius ipsa sapiente odit!</p>
            <button class="button btn">Start Looking</button>
        </div>
        <img class="w-1/3 h-auto" src="~assets/fire-extinguisher.svg" alt="fire extinguisher">
    </div>
</template>

<script>
    export default {
        data() {
            return {
                dataObject: {
                    myDate_utc: String,
                    myDate_timezone: String,
                    myDate_local: String,
                    custom: String
                }
            }
        },
        methods: {
            showTime() {
                let myDate_utc = new Date().toISOString();
                let myDate_timezone = Intl.DateTimeFormat().resolvedOptions().timeZone;
                this.dataObject.myDate_utc = new Date().toISOString();
                var offset = new Date().getTimezoneOffset();
                console.log(offset);
                console.log(Intl.DateTimeFormat().resolvedOptions().timeZone)
                this.dataObject.myDate_timezone = myDate_timezone

                var options = {
                    timeZone: myDate_timezone,
                    year: 'numeric', month: 'numeric', day: 'numeric',
                    hour: 'numeric', minute: 'numeric', second: 'numeric'
                };
                var formatter = new Intl.DateTimeFormat([], options);
                var localTime = formatter.format(new Date(myDate_utc));
                this.dataObject.myDate_local = localTime
                var currentTime = formatter.format(new Date())
                console.log('currentTime', currentTime, 'localTime', localTime)
                // console.log('utc', utc);
            }
        }
    }
</script>

<style scoped>
    .Hero {
        height: 50vh;
        position: relative;
        display: flex;
        padding: 5rem 0;
        align-items: flex-start;
        justify-content: space-between;
    }

    .text-container {
        width: 50%;
        margin-top: 4rem;
    }

    .header {
        font-weight: 900;
        font-size: 5rem;
    }

    .snippet {
        color: grey;
        font-size: 1.25rem;
    }

    .image {
        width: 27.5rem;
        margin-top: 2rem;
    }

    .overlay {
        background: rgba(0, 0, 0, 0);
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
    }

    .button {
        padding: 1rem 4rem;
        border-radius: 100rem;
        background-color: rgb(231, 81, 43);
        color: white;
        width: 20rem;
        font-weight: 700;
        transition: 0.5s;
    }

    .button:hover {
        width: 21.5rem;
    }

    @media (max-width: 500px) {
        .Hero {
            height: 40vh;

        }
    }
</style>