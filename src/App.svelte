<script>
  // Importer les dépendances nécessaires
  import svelteLogo from './assets/svelte.svg';
  import viteLogo from '/vite.svg';
  import QuestionCard from './QuestionCard.svelte'; // Vous devrez créer ce composant

  // Données pour les questions et réponses
  let questions = [
    {
      id: 1,
      number: 'Question 1',
      title: 'Votre entreprise a décidé d’acquérir une solution SaaS pour sonportail de statistiques auprès d’un éditeur et vous devez rédiger dans l’appel d’offre la partie sur les exigences techniques en termes de sobriété numérique.\n' +
        'Listez les critères qui vous semblent non négociables sous forme de user stories fictives.',
      content: `
        <div class="user-story"><b>User Story 1 :</b> En tant qu'éditeur, je dois m'assurer que ma solution est hébergée sur un serveur localisé en France pour réduire l'empreinte carbone due au transfert de données.</div>
        <div class="development">Cela implique de choisir un hébergeur dont les datacenters sont situés en France, ce qui réduit la distance parcourue par les données et donc l'énergie consommée. De plus, cela garantit une meilleure conformité avec les réglementations européennes en matière de protection des données.</div>
        <div class="user-story"><b>User Story 2 :</b> En tant qu'éditeur, je m'engage à utiliser des serveurs alimentés par des énergies renouvelables pour minimiser l'impact environnemental.</div>
        <div class="development">Opter pour des hébergeurs qui utilisent l'énergie éolienne, solaire ou hydroélectrique pour alimenter leurs serveurs. Cela contribue à réduire significativement l'empreinte carbone du service numérique.</div>
        <div class="user-story"><b>User Story 3 :</b> "En tant qu'éditeur, je dois garantir une faible consommation d'énergie de ma solution pour contribuer à la sobriété énergétique."</div>
        <div class="development">Implique des pratiques telles que l'optimisation des performances des serveurs, l'utilisation efficace des ressources et la réduction des besoins en bande passante et en stockage.</div>
        <div class="user-story"><b>User Story 4 :</b> "En tant qu'éditeur, je m'assure que ma solution est conçue pour minimiser l'utilisation de données et l'espace de stockage nécessaire."</div>
        <div class="development">Cela peut être réalisé en optimisant les algorithmes, en compressant les données, et en évitant les redondances. Une telle approche réduit non seulement l'impact environnemental, mais améliore également la performance et l'accessibilité du service.</div>
        <div class="user-story"><b>User Story 5 :</b> "En tant qu'éditeur, je dois prévoir une politique d’obsolescence logicielle responsable pour prolonger la durée de vie des équipements utilisés."</div>
        <div class="development">Il s'agit de concevoir des logiciels qui restent fonctionnels et pertinents plus longtemps, évitant ainsi le renouvellement fréquent des équipements et la génération de déchets électroniques.</div>
        `,
      isOpen: false,
    },
    {
      id: 2,
      number: 'Question 2',
      title: 'Quels éléments du cours allez-vous utiliser dans votre alternance ?',
      content: `
        <div class="element"><b>Application de la théorie du Donut :</b> Utiliser ce modèle pour évaluer et équilibrer les besoins numériques avec les limites environnementales et sociales. Par exemple, dans le développement de logiciels ou la planification de projets IT, on peut veiller à ce que les décisions prises ne dépassent pas les limites écologiques tout en répondant aux besoins sociaux fondamentaux.</div>
        <div class="element"><b>Intégration de principes d'écoconception :</b> Appliquer ces principes dès la phase de conception des projets IT. Cela implique de penser à l'efficacité énergétique, à la réduction de l'empreinte carbone, et à la durabilité des produits et services développés.</div>
        <div class="element"><b>Adoption de pratiques de sobriété numérique :</b> Cela peut se traduire par l'utilisation rationnelle des ressources numériques, comme limiter les réunions vidéo à l'essentiel, optimiser l'utilisation des emails, et encourager les pratiques d'impression responsable.</div>
        <div class="element"><b>Sensibilisation aux impacts environnementaux du numérique :</b> Organiser des ateliers ou des discussions sur l'empreinte carbone du numérique, les effets de l'obsolescence programmée, et les moyens de réduire l'impact environnemental de nos usages numériques.</div>
      `,
      isOpen: false,
    },
    {
      id: 3,
      number: 'Question 3',
      title: 'Comment évaluez-vous la maturité de sobriété numérique de votre organisation? (ou d’une autre organisation si pas encore d’alternance). Détaillez les actions déjà mises en œuvre et ce qu’il faudrait selon vous améliorer.',
      content: `
        <div class="title-element"><b>Actions Mises en Œuvre :</b></div>
        <div class="element"><b>Utilisation de serveurs verts :</b> Choix d'hébergeurs éco-responsables pour les services IT.</div>
        <div class="element"><b>Politique de recyclage :</b> Mise en place d'un système de gestion des équipements IT en fin de vie, favorisant le recyclage et la réutilisation.</div>
        <div class="element"><b>Sensibilisation :</b> Formation des employés aux bonnes pratiques environnementales, comme l'extinction des appareils non utilisés, l'optimisation des paramètres d'économie d'énergie, etc.</div>

        <div class="title-element"><b>Améliorations Nécessaires :</b></div>
        <div class="element"><b>Formation sur l'écoconception :</b> Organiser des formations régulières pour les équipes de développement sur les principes de l'écoconception.</div>
        <div class="element"><b>Politiques d'achat durable :</b> Adopter des critères écologiques et sociaux dans le processus d'achat de matériel IT.</div>
        <div class="element"><b>Augmentation de l'utilisation de logiciels open source :</b> Réduire la dépendance à des logiciels propriétaires qui peuvent encourager l'obsolescence logicielle.</div>
      `,
      isOpen: false,
    },
    {
      id: 4,
      number: 'Question 4',
      title: 'Comment imaginez-vous le numérique en 2050?',
      content: `
        <div class="element"><b>Technologies Avancées :</b> Prévision d'une évolution vers des technologies plus durables, comme l'utilisation généralisée de l'intelligence artificielle pour optimiser la consommation d'énergie et de ressources dans le numérique.</div>
        <div class="element"><b>Société et Comportement :</b> Une plus grande sensibilisation à l'impact environnemental du numérique pourrait conduire à des comportements plus responsables, privilégiant l'efficacité et la durabilité sur la consommation excessive.</div>
        <div class="element"><b>Réglementations et Normes :</b> Anticipation d'une législation plus stricte concernant l'impact environnemental des entreprises numériques, avec des normes obligatoires sur l'écoconception, la réparabilité et le recyclage des produits numériques.</div>
      `,
      isOpen: false,
    },
  ];

  // Fonction pour basculer l'état ouvert/fermé de la carte
  function toggleQuestion(id) {
    questions = questions.map(q =>
      q.id === id ? {...q, isOpen: !q.isOpen} : q,
    );
  }

</script>
<div class="background-container">
    <div class="background"></div>
    <div class="container">
        {#each questions as question}
            <QuestionCard
                    key={question.id}
                    question={question}
                    onToggle={() => toggleQuestion(question.id)}
            />
        {/each}
        <h2>Réalisé avec Vite et Svelte</h2>
        <div>
            <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
                <img src={viteLogo} class="logo" alt="Vite Logo"/>
            </a>
            <a href="https://svelte.dev" target="_blank" rel="noreferrer">
                <img src={svelteLogo} class="logo svelte" alt="Svelte Logo"/>
            </a>
        </div>
        <p>
                        <strong>M1PEX DD</strong> par <a>Hugo Da Silva.</a> M1PEX 2023-2024 - Efrei Villejuif, 94076.
                    </p>
    </div>
</div>
