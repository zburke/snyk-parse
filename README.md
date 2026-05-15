# snyk-parse

## DESCRIPTION

Parse `snyk test --json` output, aggregating by CVE/GHSA, grouped by severity.
Displays only a single affected module by default. Pass `-v` or `--verbose`
to show all affected modules.

Output is tab separated.

## USAGE

```
snyk test --json > output.json
./snyk-parse path/to/output.json
./snyk-parse path/to/output.json [-v|--verbose]
```

## SAMPLE OUTPUT

### Regular output
```
CVE-2025-6493	MEDIUM	codemirror	5.65.21	6.0.0	Regular Expression Denial of Service (ReDoS)
	@folio/circulation@12.0.1099000000000417 < codemirror@5.65.21 and 1 others
CVE-2025-58751	LOW	sirv	2.0.4	3.0.2	Directory Traversal
	@folio/stripes-build@2.0.1099000000000047 < webpack-bundle-analyzer@4.10.2 < sirv@2.0.4 and 0 others
SNYK-JS-INFLIGHT-6095116	IGNORE	inflight	1.0.6		Missing Release of Resource after Effective Lifetime
	react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6 and 14 others
platform-lsp(snapshot)*
```

### Verbose output
```
CVE-2025-6493	MEDIUM	codemirror	5.65.21	6.0.0	Regular Expression Denial of Service (ReDoS)
	@folio/checkout@13.0.1099000000000371 < @folio/circulation@12.0.1099000000000417 < codemirror@5.65.21
	@folio/circulation@12.0.1099000000000417 < codemirror@5.65.21,
CVE-2025-58751	LOW	sirv	2.0.4	3.0.2	Directory Traversal
	@folio/stripes-build@2.0.1099000000000047 < webpack-bundle-analyzer@4.10.2 < sirv@2.0.4
SNYK-JS-INFLIGHT-6095116	IGNORE	inflight	1.0.6		Missing Release of Resource after Effective Lifetime
	@folio/bulk-edit@5.1.1099000000001118 < @folio/plugin-query-builder@3.0.1099000000001415 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/checkout@13.0.1099000000000371 < @folio/circulation@12.0.1099000000000417 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/circulation@12.0.1099000000000417 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/developer@11.0.1099000000000384 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/eholdings@11.2.1099000000000356 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/lists@5.0.2099000000001059 < @folio/plugin-query-builder@3.0.1099000000001415 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/marc-authorities@8.0.1099000000001508 < @folio/quick-marc@11.0.1099000000000576 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/oai-pmh@7.0.1099000000000203 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/plugin-query-builder@3.0.1099000000001415 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/quick-marc@11.0.1099000000000576 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/receiving@8.0.2099000000000505 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/stripes-authority-components@7.1.1099000000000233 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/stripes-marc-components@2.1.1099000000000232 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	@folio/stripes@10.1.1099000000000238 < @folio/stripes-core@11.1.1099000000001765 < react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6,
	react-query@3.39.3 < broadcast-channel@3.7.0 < rimraf@3.0.2 < glob@7.2.3 < inflight@1.0.6
```
