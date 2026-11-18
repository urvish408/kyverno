# Investigation: Webhook no-op updates

Related issue: #18722

## Initial findings

The shared controller update utility uses datautils.DeepEqual
to determine whether an API update is necessary.

File: pkg/utils/controller/utils.go

The comparison is performed before setter.Update is called.

## Next steps

- Identify the fields causing repeated differences.
- Add regression coverage.
- Evaluate a safe semantic comparison.
