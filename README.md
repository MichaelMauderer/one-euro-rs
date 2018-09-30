# One Euro Filter


A fast and simple signal filter based on the work of Géry Casiez, Nicolas and Daniel Vogel. 
The original research paper describing the algorithm can be found in the [ACM digital library (paywalled)](https://dl.acm.org/citation.cfm?id=2208639) and further information, as well as other implementations, are available on the [original author's website](http://cristal.univ-lille.fr/~casiez/1euro/).  

## Example

```$rust
use one_euro_rs::OneEuroFilter;

// Set up the filter.
let frequency = 120.0;
let cutoff_min = 1.0;
let cutoff_d = 1.0;
let beta = 1.0;

let mut one_euro = OneEuroFilter::new(frequency, cutoff_min, cutoff_d, beta);

// Process some values.
one_euro.filter(1.0);
one_euro.filter(1.1);
one_euro.filter(0.9);
one_euro.filter(99999.9);
one_euro.filter(1.01);
one_euro.filter(1.04);
one_euro.filter(0.00);
```

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.