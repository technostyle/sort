/*  ====================
		Services 
	====================
*/
function arrGen(){
	var res = [];
	var arrLen = parseInt(Math.random() * 100);
	while(arrLen--)
		res.push(parseInt(Math.random() * 100));

	return res;
}

function checkSort(arr){
	for(var i = 0; i < arr.length - 1; i++) {
		if (arr[i] > arr[i + 1]) 
			return false;
	}
	return true;
}

function swap(arr, i, j) {
	var temp = arr[i];
	arr[i] = arr[j];
	arr[j] = temp;
}

/*  ====================
		End of Services 
	====================
*/

function bubbleSort(arr) {
	for(var i = 1; i < arr.length; i++) {
		for(var j = 0; j < arr.length - i; j++) {
			if (arr[j] > arr[j + 1])
				swap(arr, j, j + 1);
		}
	}
	return arr;
}

function quickSort(arr, beg, end) {

	if (end - beg < 2)
		return;

	var medElem = arr[beg];
	var i = beg, j = end - 1;

	while(i < j) {
		
		while (arr[i] < medElem) // i always < end
			i++;

		while (arr[j] >= medElem && j > beg )
			j--;

		if (i < j) {
			swap(arr, i, j);
			i++;
			j--;
		}
	}

	if(i === end - 1)
		j = end - 1;

	else if (j === beg)
		i = beg;

	else if (i === j )
		(arr[i] < medElem) ?  i++ : j--;

	quickSort(arr, beg, i);
	quickSort(arr, j + 1, end);
}

function heapSort(arr, size) {
	if (size === 1)
		return;

	if (size % 2 === 0 && arr[size - 1] > arr[size - 2]) {
		swap(arr, size - 1, size - 2);
	}

	for (var i = size - 1 - (size % 2 === 0); i > 0; i -= 2) {

		var node = i / 2 - 1;

		if (arr[node] < arr[i])
			swap(arr, node, i);

		if (arr[node] < arr[i - 1])
			swap(arr, node, i - 1);
	}

	swap(arr, 0, size - 1);
	heapSort(arr, size - 1);
}

/* ===== test ======= */

var arr = arrGen();
print(arr);
print(checkSort(arr));
//arr = bubbleSort(arr);
quickSort(arr, 0, arr.length);
print("quickSorted --- " + checkSort(arr));

var arr = arrGen();
print(arr);
print(checkSort(arr));
heapSort(arr, arr.length);
print("heapSorted --- " + checkSort(arr));
