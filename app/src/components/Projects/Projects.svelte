<script>
import SectionContent from '../SectionContent/SectionContent.svelte';
import SectionTitle from '../SectionTitle/SectionTitle.svelte';
import ProjectCard from './ProjectCard.svelte';

const projects = [
    {
        name: 'Core Technologies Team',
        description: 'Led a team responsible for maintaining and developing core AI technologies and designing and delivering services fundamental to the core product offering. Made technical contributions to the roadmap; also acted as hiring and project manager for the team.' ,
        role: 'Engineering Manager [Clinc]',
        start: '2022',
        end: '2022',
        image: '../img/projects/clinc.png',
        link: 'http://clinc.com'     
    },
    {
        name: 'Natural Language Understanding Features',
        description: 'Used Rust and rust_bert to implement topic detection and machine translation research projects for production inference in a high-performance computing environment.',
        role: 'Software Engineer [Deepgram]',
        start: '2022',
        end: '2022',
        image: '../img/projects/dg-nlu.png',
        link: 'https://deepgram.com/product/speech-understanding/'
    },
    {
        name: 'Syng',
	description: 'Designed, developed, and maintain an open-source, cross-platform Chinese-to-English dictionary app and study toolkit.',
        role: 'Personal Project',
        start: '2016',
        end: 'Present',
        image: '../img/projects/syng.png',
        link: 'http://getsyng.com/'
    },
    {
        name: 'AI Testing',
	description: 'Designed, developed, and maintained the AI Testing feature of the Conversational AI Platform. Started from requirements document and developed project scope with input from relevant stakeholders. Designed wireframes, developed front-end, and maintained project after launch. ',
        role: 'Software Engineer [Clinc]',
        start: '2018',
        end: '2019',
        image: '../img/projects/testing.png',
        link: 'http://clinc.com'
    },
    {
        name: 'Custom Banking Conversational AI',
	description: 'Scoped, developed, and maintained conversational AI solutions for existing and potential banking customers. Maintained over 40 training and testing datasets. Worked closely with the clients to ensure successful project delivery.',
        role: 'Solutions Architect [Clinc]',
        start: '2019',
        end: '2020',
        image: '../img/projects/banking.png',
        link: 'http://clinc.com' 
    },
    {
        name: 'Finie',
	description: `Led a team of developers to build the company’s flagship conversational AI product. Used Gitlab CI/CD to develop a data version control system. Conducted code and dataset reviews. Work closely with the product team to create a roadmap and deliver on milestones.`,
        role: 'Tech Lead [Clinc]',
        start: '2020',
        end: 'Present',
        image: '../img/projects/finie.png',
        link: 'https://clinc.com/finie/'
    },
    {
        name: 'chinese-dictionary',
        description: 'A searchable Chinese / English dictionary npm module with helpful utilities.',
        role: 'Package',
        start: '2021',
        end: 'Present',
        image: '../img/projects/chinese-dictionary.png',
        link: 'https://www.npmjs.com/package/chinese-dictionary'
    },
    {
        name: 'chinese_dictionary',
        description: 'A searchable Chinese / English Rust crate with helpful utilities',
        role: 'Package',
        start: '2020',
        end: 'Present',
        image: '../img/projects/chinese_dictionary.png',
        link: 'https://crates.io/crates/chinese_dictionary'
    },
    {
        name: 'character_converter',
        description: 'Turn Traditional Chinese script to Simplified Chinese script and vice-versa. Check string script to determine if string is Traditional or Simplified Chinese Characters.',
        role: 'Package',
        start: '2020',
        end: 'Present',
        image: '../img/projects/character_converter.png',
        link: 'https://crates.io/crates/character_converter'
    },
    {
        name: 'chinese_detection',
        description: 'Classify a string as either English, Chinese, or Pinyin.',
        role: 'Package',
        start: '2020',
        end: 'Present',
        image: '../img/projects/chinese_detection.png',
        link: 'https://crates.io/crates/chinese_detection'
    },
    {
        name: 'prettify_pinyin',
        description: 'Turn tone numbers into tone marks.',
        role: 'Package',
        start: '2017',
        end: 'Present',
        image: '../img/projects/prettify_pinyin.png',
        link: 'https://crates.io/crates/prettify_pinyin'
    },
    {
        name: 'hsk',
        description: 'Return HSK level for Simplified Chinese Characters',
        role: 'Package',
        start: '2020',
        end: 'Present',
        image: '../img/projects/hsk.png',
        link: 'https://crates.io/crates/hsk'
    },
    {
        name: 'chinese_segmenter',
        description: 'Segment Chinese sentences into component words using a dictionary-driven largest first matching approach.',
        role: 'Package',
        start: '2020',
        end: 'Present',
        image: '../img/projects/chinese_segmenter.png',
        link: 'https://crates.io/crates/chinese_segmenter'
    }
].sort((a, b) => {
    let order;

    if(a.start < b.start) {
        order = -1;
    } else if(a.start > b.start) {
        order = 1;
    } else {
        order = 0;
    }

    return order;
});
</script>

<style>
/* iPad Portrait */
@media (max-width: 1024px) {
    .projects-section--content {
        grid-template-columns: repeat(1, 1fr) !important;
    }
}
.projects-section--content {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: var(--space--large);
}
</style>

<SectionContent color="light">
	<SectionTitle>
		<h1 id="projects">Projects</h1>
	</SectionTitle>
    <div class="projects-section--content">
        {#each projects as project}
            <ProjectCard name="{project.name}"
                description="{project.description}"
                role="{project.role}"
                start="{project.start}"
                end="{project.end}"
                image="{project.image}"
                link="{project.link}" /> 
        {/each}
    </div>
</SectionContent>
