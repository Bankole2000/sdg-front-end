<template>
  <div class="home">
  <Title title="Welcome to the Covid-19 Estimator"/>
  <main>
    <h3>The Covid-19 Impact Estimator</h3>
  <input type="text" name="population" data-population>
  <input type="text" name="timeToElapse" data-time-to-elapse>
  <input type="text" name="reportedCases" data-reported-cases>
  <input type="text" name="totalHospitalBeds" data-total-hospital-beds>
  <select name="periodType" id="">
    <option value="days">days</option>
    <option value="weeks">weeks</option>
    <option value="months">months</option>
  </select>
    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit voluptatibus explicabo laborum
    mollitia vitae, quisquam omnis autem placeat sint impedit pariatur quidem ullam earum eius
    excepturi rem sed natus optio modi repellendus suscipit, tempora et. Animi dolorum vitae nemo
    fugit, id illo laborum nisi nihil incidunt labore ullam repellendus tempore eaque quae inventore
    itaque deleniti impedit rem cumque explicabo illum suscipit eum temporibus voluptas. Neque at
    voluptate beatae eaque necessitatibus suscipit tenetur ipsa similique, ipsam mollitia aspernatur
    asperiores quis nihil magni facilis architecto voluptatibus! Sequi adipisci fugiat magni
    quisquam repudiandae officia nostrum possimus voluptatibus nemo consectetur saepe ut, vero dolor
    sunt laboriosam quibusdam assumenda incidunt mollitia provident. Rem numquam, quo excepturi
    tenetur ad vitae, odio vel hic, recusandae aliquid delectus eligendi magni dignissimos quisquam
    ut nam omnis iusto perspiciatis suscipit alias adipisci libero? Ut enim, optio voluptate
    excepturi vero nam perspiciatis molestias accusamus. Ratione, esse autem incidunt suscipit earum
    saepe modi, animi molestias cumque optio non recusandae ab labore nulla mollitia. Mollitia iste
    placeat doloribus architecto, quidem magnam a, vitae consectetur perspiciatis, vel provident quo
    nam dolores rerum voluptatum laborum officia voluptatibus illum optio facere iure! Officiis id
    iure facere velit quisquam totam consectetur sunt tempore quis ipsum, magnam autem, perferendis
    nulla animi corporis officia, qui assumenda deserunt? Recusandae ullam, accusantium a,
    dignissimos, commodi repellendus est animi aliquid placeat nobis molestias! Error, quidem est.
    Aspernatur quod hic minima at possimus doloremque, omnis vel doloribus quisquam odit pariatur
    veritatis! Sint nam cum in molestias distinctio. Natus nisi, aut aliquam atque sint dolores vel
    fuga deleniti architecto doloribus. Tempore consequatur officiis animi officia in fuga ipsum
    deleniti, eos ut optio culpa fugit nisi accusantium libero fugiat voluptate similique magnam
    nam? Blanditiis repudiandae facere assumenda, pariatur quia aperiam beatae dolorem molestiae
    vel, exercitationem reiciendis ratione provident, consectetur a vitae nemo veniam enim? Fugit
    molestiae in reprehenderit facere sunt voluptate natus nemo amet nisi aliquam quidem ex
    excepturi provident quae eveniet at, illum temporibus minus a? Laborum doloribus accusamus,
    cupiditate voluptatibus hic ut, illum ratione facere quam inventore nostrum at nesciunt, iure
    quisquam. Non qui tempora molestias magnam quia! Dolores nulla consectetur repellendus accusamus
    neque molestias minus at libero eveniet iure? Quas inventore officiis reprehenderit aliquid odio
    ratione sunt vitae. Non amet voluptas doloremque incidunt deleniti iusto adipisci perspiciatis
    tempora, impedit fugiat aspernatur sunt odio aliquid voluptatem beatae et possimus suscipit
    facilis fugit ea inventore maxime voluptate id sit. Laboriosam quae ducimus distinctio
    molestiae, maxime fuga beatae hic, quas deserunt numquam officiis impedit repellat id autem
    exercitationem modi praesentium veritatis possimus, dolores nisi recusandae voluptatibus.
    Dolorem aliquid reiciendis deleniti tempora aut eveniet, ducimus aperiam eos temporibus quidem
    nihil inventore, natus non, error velit? Officiis qui autem consequatur in minima magni
    consequuntur commodi deleniti iure, perferendis libero accusamus repudiandae sapiente nam
    dolores id? Ullam, nulla, quod illum dolores mollitia possimus veritatis earum nisi,
    reprehenderit officia deleniti impedit nostrum sequi molestiae reiciendis! Omnis nihil vel
    pariatur exercitationem maiores hic voluptate! Consequuntur dolore, vero quas quod nostrum, esse
    minima iste non autem, a sed dolorem ipsum! Commodi!


    <img alt="Vue logo" src="../assets/logo.png">
    <Index msg="Welcome to Your Vue.js App"/>

  </main>
  </div>
</template>

<script>
// @ is an alias to /src
import Title from '@/components/Title.vue';
import Index from '@/components/Index.vue';

export default {
  name: 'Home',
  components: {
    Title,
    Index,
  },
};
</script>
