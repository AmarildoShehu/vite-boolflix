<script>
import { store } from '../data/store.js';
import FilmCard from './filmCard.vue';
export default {
    name: 'ListFilms',
    data: () => ({
        store
    }),
    components: {
        FilmCard
    }
}
</script>