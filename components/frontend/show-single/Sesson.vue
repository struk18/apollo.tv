<template>
<section class="container-fluid seasons">
    <ul class="trending-pills d-flex nav nav-pills align-items-center text-center" role="tablist">
        <li v-for="season in sessonData.seasons" :key="season" class="nav-item">
            <a class="nav-link" data-toggle="pill" :href="'#season' + season" role="tab" aria-selected="false">Season {{ season }}</a>
        </li>
    </ul>
    <div class="tab-content">
        <div v-for="season in sessonData.seasons" :key="season" :id="'season' + season" class="tab-pane fade" :class="[ season==1 ? ' active show':'' ]" role="tabpanel">
            <div class="block-space">
                <b-row>
                    <b-col md="6" class="col-1-5 iq-mb-30" v-for="(item, index) in sessonData.episodes[season - 1]" :key="index">
                        <div class="epi-box">
                            <div class="epi-img position-relative">
                                <img :src="item.screenshot" class="img-fluid img-zoom" alt="">
                                <div class="episode-number">{{item.episode}}</div>
                                <div class="episode-play-info">
                                    <div class="episode-play">
                                        <nuxt-link :to="{ path: '/frontend/tvshow-detail', 
                                              query: {
                                                imdb_id: sessonData.imdb_id,
                                                season: season,
                                                episode: item.episode
                                                } }" >
                                            <i class="ri-play-fill"></i>
                                        </nuxt-link>
                                    </div>
                                </div>
                            </div>
                            <div class="epi-desc p-3">
                                <div class="d-flex align-items-center justify-content-between">
                                    <!-- <span class="text-white">{{item.date}}</span> -->
                                    <span class="text-primary">{{item.duration}} min</span>
                                </div>
                                <h6 class="epi-name text-white mb-0">{{item.plot}}</h6>
                            </div>
                        </div>
                    </b-col>
                </b-row>
            </div>
        </div>
    </div>
</section>
</template>

<script>
export default {
    name: 'Sesson',
    components: {},
    mounted() {},
    props: {
        data: {
            type: Object,
            required: false
        }
    },
    data() {
        return {
            sessonData: this.data,
            seasonData1: [
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '1', date: '11 Aug 20', time: '30m', text: 'Lorem Ipsum is simply dummy text' },
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '2', date: '12 Aug 20', time: '35m', text: 'Lorem Ipsum is simply dummy text' },
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '3', date: '14 Aug 20', time: '20m', text: 'Lorem Ipsum is simply dummy text' },
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '4', date: '15 Aug 20', time: '40m', text: 'Lorem Ipsum is simply dummy text' },
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '5', date: '16 Aug 20', time: '25m', text: 'Lorem Ipsum is simply dummy text' },
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '6', date: '20 Aug 20', time: '35m', text: 'Lorem Ipsum is simply dummy text' },
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '7', date: '21 Aug 20', time: '40m', text: 'Lorem Ipsum is simply dummy text' },
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '8', date: '23 Aug 20', time: '45m', text: 'Lorem Ipsum is simply dummy text' },
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '9', date: '24 Aug 20', time: '25m', text: 'Lorem Ipsum is simply dummy text' },
                { image: require('../../../assets/images/frontend/episodes/01.jpg'), episode: '10', date: '25 Aug 20', time: '30m', text: 'Lorem Ipsum is simply dummy text' }
            ]
        }
    }
}
</script>
