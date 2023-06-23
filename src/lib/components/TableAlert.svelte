<script>
    import { Table, tableMapperValues } from '@skeletonlabs/skeleton';

    

    const sourceData = [
	{ position: 1, nom: 'Hydrogen', code: 1.0079, message: 'Alerte : lorem ipsum bla bla bla bla bla bla bla bla  H' },
	{ position: 2, nom: 'Helium', code: 4.0026, message: 'Alerte : lorem ipsum bla bla bla bla bla bla bla bla  He' },
	{ position: 3, nom: 'Lithium', code: 6.941, message: 'Alerte : lorem ipsum bla bla bla bla bla bla bla bla  Li' },
	{ position: 4, nom: 'Beryllium', code: 9.0122, message: 'Alerte : lorem ipsum bla bla bla bla bla bla bla bla  Be' },
	{ position: 5, nom: 'Boron', code: 10.811, message: 'Alerte : lorem ipsum bla bla bla bla bla bla bla bla  B' },
    ];

    const tableSimple = {
	// A list of heading labels.
	head: ['Nom', 'Code', 'Message'],
	// The data visibly shown in your table body UI.
	body: tableMapperValues(sourceData, ['nom', 'code', 'message']),
	// Optional: The data returned when interactive is enabled and a row is clicked.
	meta: tableMapperValues(sourceData, ['position', 'nom', 'code', 'message']),
    };
</script>

<Table source={tableSimple} />
