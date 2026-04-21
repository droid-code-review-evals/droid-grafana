# Review Guidelines - Structured Bug Checklist

## Mandatory Checks Per File

For EVERY modified file in the diff, systematically check:

### Data Flow Checks
- [ ] Are all function parameters validated before use?
- [ ] Are return values from external calls checked for null/error?
- [ ] Are type conversions safe (datetime to number, string to int)?
- [ ] Are dictionary/map accesses guarded against missing keys?

### Logic Checks  
- [ ] Do boolean expressions evaluate correctly in all cases?
- [ ] Are comparison operators correct (< vs <=, == vs ===)?
- [ ] Do feature flags / conditional branches work as intended?
- [ ] Are defaults reasonable and not evaluated at wrong time?

### Concurrency Checks
- [ ] Are shared mutable state accesses thread-safe?
- [ ] Are read-modify-write sequences atomic?
- [ ] Are locks acquired in consistent order?

### Integration Checks
- [ ] Do interface/abstract method implementations match contracts?
- [ ] Are API call parameters in the correct order?
- [ ] Do database queries use correct column names and types?
- [ ] Are cache keys unique and unambiguous?

Report ANY check that fails with evidence from the diff.
