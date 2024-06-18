# ASCAT algorithm for GATK segments

This repository contains a reimplementation of the
[ASCAT](https://pubmed.ncbi.nlm.nih.gov/20837533) algorithm designed to work
with segments computed by GATK's
[ModelSegments](https://gatk.broadinstitute.org/hc/en-us/articles/360037225892-ModelSegments)
tool. In addition, the implementation can use TP53 VAFs as additional evidence
in the model selection process. Overall, the model selection process is slightly
different from the original ASCAT algorithm, as it uses a penalized score
instead of step-by-step relaxation of constraints until a model is found.

## Usage

```
Usage: ./ascat-on-gatk.R [options] segment_model_file


Options:
	--snp-purity=SNP-PURITY
		Optional truncal SNP (TP53, for example) for for additional purity evidence. Format: chrom,pos,altCount,refCount

	--sample=SAMPLE
		The sample identifier

	--segment-output=SEGMENT-OUTPUT
		Output tsv file for the segments

	--estimate-output=ESTIMATE-OUTPUT
		Output tsv file for purity, ploidy, and goodness of fit

	--sunrise-output=SUNRISE-OUTPUT
		Output file for the sunrise plot

	-h, --help
		Show this help message and exit
```

## License

Written by Kari Lavikka

Licenced under CC0 1.0 Universal (CC0 1.0) Public Domain Dedication.
